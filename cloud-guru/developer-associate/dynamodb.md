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