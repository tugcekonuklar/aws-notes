## Introduction to DynamoDb

* Fast and flexible low latency NoSql database.
    * it is alternative more rigid databases like Oracle and sql
* Fully managed Database
    * Supports Key-value data models. Supports documented models like Json, HTML and XML
* Use cases:
    * It is a great fit for mobile, web, gaming and tech, IOT and many other applications.
* DynamoDB is serverless
    * Integrates with Lambda well
    * can configure automatically scale
    * popular chose for serverless architectures.
* Performance:
    * Stored SSD (Solid State Disk), which helps to give fast performance reads and writes.
* Resilience:
    * The underlying hardware supporting the DynamoDB table always spread across 3 geografically distinct data centers
      to avoid any single point of failure if any one of lost or unavaible.
* Consistency:
    * 2 options to chose consistency
        * Eventual consistency reads (default):
            * Consistency across all copies of data is usually reached within a second
            * That mean if you changed a data second ago then DynamoDb needs to return update data.
            * However can take up one second for new writes or updates the data to be reflected when you read data from
              DynamoDb.
            * Best for reads performance
        * Strong consistency reads:
            * Always reflects all successful writes.
            * All writes are reflected all 3 locations at once
            * You dont need to wait up to one second to across all locations.
            * This is best for read consistency.
* Also supports fpr ACID transactions called Dynamo DB transactions.
    * [Amazon DynamoDB Transactions: How it works](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/transaction-apis.html)
    * This provide the ability of ACID Transactions
        * Atomic: all-or-nothing transaction
        * Consistency: consistence with data validation rules
        * Isolation: Transactions happens in isolations independently one on another not impacting each other.
        * Durability: They dont disappear if system crash
    * Reads/writes multiple items across multiple items tables as an all-0r-nothing operation
* DynamoDb consist tables items and attributes.
* Primary Keys:
    * it allows us to query data in table
    * it stores and retrieves data based on PK
    * 2 types PK
        * Partition Key:
            * Based on unique attribute, ie customerID, orderId .
            * Value of the partition key is the imput on an internal hash function which determines the partition or
              physical location on which data is stored.
            * if you use Partition key as PK then it is not allowed to have 2 items have same partition key
        * Composite Key (partition + sort key):
            * made up combination Partition key and sorted key.
            * You would use this combination key in a situation where the partition key is not necessary unique within
              your table.
            * i.e forum posts table, users post multiple messages, in this case userId can not be unique and combination
              will be userId(partition) + timestamp(sort key)
            * This gives us a unique combination for your primary key
                * That means you can have same partition key,but they have to have different sortKey value
            * Storage:
                * All items with the same partition key are stored together and then sorted according to sortkey values
                  and this allow to store multiple items using same partition key.

## Demo creating DynamoDb with AWS CLI

* Command to query Dynamodb from EC2 command line - just remember replace the region with the correct one for your
  database
    * `aws dynamodb get-item --table-name ProductCatalog --region eu-west-2 --key '{"Id":{"N":"205"}}'`
* Creat a Dynamo DB commands
    ```
    1) Check your IAM user permissions:
    
    aws iam get-user
    
    2) Creating the SessionData table:
    
    ***LINUX or MAC USERS***:
    aws dynamodb create-table --table-name SessionData --attribute-definitions \
    AttributeName=UserID,AttributeType=N --key-schema \
    AttributeName=UserID,KeyType=HASH \
    --provisioned-throughput ReadCapacityUnits=5,WriteCapacityUnits=5
    
    3) Populate SessionData Table:
    
    aws dynamodb batch-write-item --request-items file://items.json
    ```

## DynamoDb Access Control

* How we control access to Dynamo Db
    * IAM : authentication and Access control is managed by AWS IAM
    * IAM Permission: create IAM users with specific permission to access and create DynamoDb
    * IAM Roles: create IAM roles to give temporary access to DynamoDb.
* Restricting User Access:
    * you can use special **IAM condition** to restrict user access to only their own records.
    * Only the data which is related with user can reach.
    * For example gaming solution you show peoples score, you want to be sure they can not see other peoples scores,
      then you can add **IAM condition**
    * This can done by adding **condition** to an IAM Policy to allow access only to items where the partition key value
      matches their User_Id.
    * IAM condition paramater **dynamodb:LeadingKeys** allows users to access only the items where the partition
      key-value
      matches their User_ID
    * ![IAM Policy sample](img/dynamo-1.png)

## Secondary Indexes

* Secondary index allows you to perform more flexible queries
* Allows query based on an attribute which not the primary key
* DynamoDb allows you to run a query on non-primary key attributes using **global secondary indexes** and **local
  secondary indexes**
* A secondary index allows you to perform fast queries on specific columns in a table. You select the columns that you
  want to included in index and run your searches on the index, rather than on the entire table.
* Because you are running the search required columns, it means your queries a lot faster more efficient to run the
  query on the entire data set.
* Local Secondary Index:
    * Primary Key: A local secondary index is an index that can only be created when you are creating your table and it
      has same
      partition key as your original table.
    * Different View:  but ot has a different sort key at gives you a different view of data, because data will be
      orginize according to
      an alternative sorted key
    * Fast Query: Any queries based on this sortkey are much faster using the index than the main table.
    * Add at creation time: Can be created only when you create on creation time. You can not add, remove or modify
      after it later.
* Global secondary indexes:
    * Flexible: you can create secondary index when ever you like, you can create on table creation or add
      later.
    * Completely different Primary Key: Different partition key and sort key from table itself.
    * Data view: this gives completely different view of your data.
    * Speed up: ofc speeds up the queries related to this alternative partition and sort keys.
* ![indexes differents](img/dynamo-2.png)

## Scan vs Query Api Calls

* Query:
    * A query finds items in a table based on the **primary key** attribute and a distinct value to search
        * For example: selecting an item where userId=200 will select all attributes of the item ie firstname lastname
    * And you can use optional sort key name and value to refine the query results.
        * For example: your sortkey is timestamp, you can select items with timestamp of the last 7 days.
    * By default query returns all attributes of the item, but if you wany to return specific attributes you want you
      can use 'ProjectionExpression'
    * SortKey: Results always sorted by sorted ley value
    * Numeric Order: default is ascending numeric ordering
    * ASCII: if there is ascii characters, it orders ASCII characters also ascending orders
    * Reverse the order: You can reverse the order by setting "ScanIndexForward=false"
        * "ScanIndexForward" just use for query only not scan
    * Eventually consistent: queries are eventually consist
    * Strongly Consistent: You need to explicitly set query to be consistent
* Scan:
    * Scan operation examines every item in the table.
    * By default it returns all attributes.
    * You can use "ProjectionExpression" param to refine your results. and you can also filter once it has been run.
    * Even you apply filter, it dumps all data from table then apply the filter to show only the results we are looking
      for.
* Query or Scan:
    * Query is more efficient than Scan because Scan dumps all data in the table first then apply filters to provide
      desired results .
    * This is adding extra steps removing data you dont want, as the table grows the scan action will be longer.
    * A scan operation on a large table can use up the provisioned throughput for a large table in just a single
      operation.
* Ways to improve performance
    * You can reduce impact of the query and scan by adding a smaller page size which uses fewer read operation.
        * For example you set up page size 40
        * Runnig a larger number of smaller operations will allow other request to success without throttling.
        * Avoid scan operations as much as you can. Instead, design your queries that you can use Get, Query or
          BatchGetItem APIs
* How to improve Scan Operation?
    * Sequential by Default:
        * A scan operation process data sequentially returning 1MB increments before moving on to retrieve teh next 1MB
          data
        * Scans 1 partition at the time.
    * Parallel Scans:
        * You can configure DynamoDB to use parallel scans instead by logically dividing by table or index into segments
          and scanning each segment in parallels
        * BUT if your table has heavy read and write activity from other applications then can cause some performance
          issues.
    * Isolate: You can also isolate your scan operations to specific tables and segregate them from your
      mission-critical traffic.
        * Even it means writing data 2 different tables this is just another way to improve performance.

## Using DynamoDB APi calls:

* While we use AWS CLI and use get-item command it is using/calling GetItem API of the dynamoDB.
* Commonly used APIs:
    * ![Commonly used apis 1](img/dynamo-3.png)
    * ![Commonly used apis 2](img/dynamo-4.png)
* To be able run the command user needs to have the right IAM permission required for each operation that we would like
  to allow.For example to run put=item command user needs to have permission to call PutItem 
* [Commands in DynamoDB](https://awscli.amazonaws.com/v2/documentation/api/latest/reference/dynamodb/index.html)