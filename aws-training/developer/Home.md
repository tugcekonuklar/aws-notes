# Developing Solution in AWS

# What is Cloud Computing?

* Cloud computing enables you to stop thinking of your infrastructure as hardware, and instead think of it (and use it)
  as software.

## Models of Cloud Computing

* **Infrastructure as Service (IaaS):** Basic building blocks for cloud IT
    * Network features
    * Computer
    * Data storage space
* **Platform as a service (PaaS):** Enables you to run applications without the need to manage underlying
  infrastructure (
  for example hardware and operation system)
* **Software as a service (SaaS):** Provides you with a completed product that the service provider runs and manages

### Amazon Resource Name (ARN)

* You can use Amazon Resource Names (ARNs) to uniquely identify AWS resources or groups of resources.
  <img src="./img/17.png" alt="alt text" width="500" height="300">

## AWS service Stack

<img src="img.png" alt="alt text" width="500" height="300">

## AWS Foundation Services

<img src="img.png" alt="alt text" width="500" height="300">

* AWS provides several foundation services
    * Compute:
        * Amazon Elastic Compute Cloud (EC2) id AWS compute services
        * Easy to boot new server
        * You can combine EC2 with Elastic Load Balancing and Auto Scaling services to develop a high availability and
          high-performance infra for your apps.
    * Networking:
        * Networking group provides a DNS
            * DNS can give direct control over your AWS and interaction with EC2 instances over your network.
    * Storage:
        * Provides several type of storage options

### Compute

* **Amazon Elastic Compute Cloud (EC2) :**
    * Provides pay-as-you-go pricing
    * Creates Amazon Machine Images (AMIs)
    * Add / terminate instances as needed
    * Pause / Resume instances
    * Scalability:
        * Scale in -> add more instance
        * Scale out -> removes instance
        * Scale up -> extend current memory , not recommended
        * Scale down -> downgrad current memory , not recommended
    * Pricing
        * On-demand
        * Reserved instance
        * Spot instance: is %90 less than on-demand.
            * Spot Instances are unused EC2 capacity; the price you pay is determined by the supply and demand for the
              instance
            * You can specify max price willing to pay by instance hour
                * can reduce the cost of running your Hadoop or Spark clusters, increase your compute capacity and
                  throughput without increasing your budget, or both
            * Spot Instances are also available to run for a predefined duration

<img src="img.png" alt="alt text" width="500" height="300">

* General purpose instances provide a balanced set of resources and a low-cost platform that is well suited for a wide
  variety of applications.
* Compute optimized instances provide a higher level of processing performance and are ideal for applications that
  require higher absolute CPU and memory capacities. For example, these include encoding applications, high-traffic
  content management systems, and Memcached applications.
* Memory optimized instances offer large memory sizes for high-throughput applications, including database and
  memory-caching applications.
* Accelerated Computing instances have proportionally more CPU resources than memory (RAM) and are well suited for
  compute-intensive applications. Various high-storage and cluster-computer instance types are also available
* [AWS instance Types](http://aws.amazon.com/ec2/instance-types/)


* **Amazon Elastic Load Balancing :**
    * Distributes traffic accross multiple targets, such as Amazon EC2 instances in multiple available zone, containers
      and IP addresses
    * Supports health check of EC2 instances
    * Supports routing and load balancing of EC2 instances.

<img src="./img/6.png" alt="alt text" width="500" height="300"></br>
<img src="./img/7.png" alt="alt text" width="500" height="300">

* **AWS Lambda** :
    * AWS Lambda can automatically run code in response to multiple events, such as:
        * HTTP requests through Amazon API Gateway
        * Modifications to objects in Amazon S3 buckets
        * Table updates in Amazon DynamoDB
        * State transitions in AWS Step Functions

## AWS Platform Services

* Platform services devided 4 categories
* Database: several options to store data based on the type
    * SQL: Amazon Relational Database (Amazon RDS)
    * NoSQL :
        * AWS DynamoDb is a great key value database
        * AWS Document DB : Document DB
        * AWS ElasticCache, for Redis or MemCache
        * Amazon Redshift for data warehouse
* Analytics: provides services to analyse big data
    * Amazon Kinesis
    * Amazon EMR
* Development Tools:
    * AWS CodeCommit is a source control service is combined with development services such as
        * AWS CodeDeploy
        * AWS Elastic Beanstalk
        * AWS Cloud Formation
    * Helps to create robust DevOps model.
* Mobile:
    * AWS Simple Notification Service SNS for notification.
    * Amazon Cognito for authentication and saving mobile user data
    * Amazon Pinpoint to measure and analyse mobile application usage

<img src="img.png" alt="alt text" width="500" height="300">

## Architecture Evaluation

<img src="img.png" alt="alt text" width="500" height="300">

# AWS Identity and Access Management

* **AWS IAM(Identity Access Management) :**
    * IAM enables you to create and manage AWS users and groups. With IAM, you can set up roles and policies to control
      access to AWS services.
    * Security of the Cloud = AWS
    * Security in the Cloud = You
    * To see who changed user account? Configure AWS CloudTrail or not.
    * When you create IAM **policies**, follow the principle of least privilege—that is, granting only the permissions
      required to perform a task. Determine what users need to do and then craft policies that allow the users to
      perform only those tasks
    * A **role** has policies granting access to specific services and operations.

<img src="./img/13.png" alt="alt text" width="500" height="300"></br>
<img src="./img/14.png" alt="alt text" width="500" height="300"></br>
<img src="./img/15.png" alt="alt text" width="500" height="300"></br>

* Example of IAM Policy

<img src="./img/16.png" alt="alt text" width="500" height="300"></br>

* IAM Permission Type
    * Identity-based permissions are attached to the IAM user and indicate what the user is permitted to do.
    * Resource-based permissions are attached to a resource and indicate what a specified user (or group of users) is
      permitted to do with it. Amazon S3, Amazon Simple Queue Service (Amazon SQS), Amazon Simple Notification Service (
      Amazon SNS), and AWS OpsWorks are the only services that support resource-based permissions.

<img src="./img/18.png" alt="alt text" width="500" height="300"></br>
<img src="./img/19.png" alt="alt text" width="500" height="300"></br>

* IAM Policy Types

<img src="./img/20.png" alt="alt text" width="500" height="300"></br>

* IAM Policies Evaluation Logic
    * Use policies to fine-tune permissions granted to IAM users, groups, and roles.
    * Policies can be in a variety of formats. Because policies are in JSON format, you can use them with a
      version-control system.
    * It’s good practice to define least privilege access to each user, group, or role. Then you can customize access to
      specific resources by using an authorization policy.
    * To determine whether the request should be allowed or denied, these rules are followed:
        * By default, all requests are denied. (In general, requests made by using the account/root credentials for
          resources in the account are always allowed.)
        * An explicit allow overrides this default.
        * An explicit deny overrides any allows.
    * All policies that have been applied to the IAM entity are evaluated. If there is a conflict, the most restrictive
      policy is applied. For example, when one policy allows an acMon and another policy denies an acMon, the policy
      that denies the acMon is applied

  <img src="./img/21.png" alt="alt text" width="500" height="300"></br>

* The example policy gives users access to only the following:
    * The DynamoDB table whose name is represented by table-name.
    * The AWS account's corporate Amazon S3 bucket whose name is represented by bucket-name and all the objects it
      contains.
    * The policy includes an explicit deny ("Effect":"Deny" element). Used with the NotResource element, this helps to
      ensure that the users cannot use any AWS actions or resources. The exception is those specified in the policy,
      even if permissions have been granted in another policy. (An explicit deny statement takes precedence over an
      allow statement.)

* Overview of Authentication
    * For example, if you are developing a mobile photo app on AWS, you must sign in to AWS using credentials to create
      the AWS environment for that app. Signing in to AWS here requires that you authenticate with AWS (AWS
      authentication).
    * After the environment has been set up, the end user should be able to sign in to their photo application. Signing
      in to the photo application requires the user to authenticate with their application (
      application authentication).
    * If the user takes a picture using their photo app and uploads it to AWS, authentication occurs with AWS (AWS
      authentication).
    * Finally, the photos that have been uploaded to the S3 bucket can cause a backend job to update the RDS database
      with an entry for the uploaded photo. This job requires database authentication

  <img src="./img/22.png" alt="alt text" width="500" height="300"></br>

* **Authentication via Developer Tools**

* IAM Authentiation in CLI and SDK

<img src="img3.png" alt="alt text" width="500" height="300">

* Best Practices:
    * not using your AWS account root user credentials. Instead, create separate IAM users with their own access keys
      for each project, and tailor the permissions of the users specific to those projects.
    * In general,recommended you use IAM roles when running your application on Amazon EC2 and use credential profiles
      or environment variables elsewhere.

* Security Credential Priority Order

<img src="img4.png" alt="alt text" width="500" height="300">

# Developer Tools

* **AWS Cloud9 :** Creates a Development environment
    * Has all apps you can download

* **AWS SDK**
    * helps to build infra with code

* **AWS CLI:**
* Aws command, followed by the three parts:
    * Command – The top-level service that you are calling (for example, Amazon EC2, Amazon CloudWatch). For a list of
      currently supported services, see [Cli Doc](http://docs.aws.amazon.com/cli/latest/reference/). Using the example
      script, Amazon EC2 is being called.
    * Subcommand – The operation to perform on that service (for example, run-instances, put-metric-data). In this
      Amazon EC2 example, the run-instances subcommand requests the creation of a new Amazon EC2 instance.
    * Parameters – Any arguments required to perform the operation. Argument names are preceded by two dashes (--). For
      example, to run the Amazon EC2 run instances operation, pass in a number of parameters, such as the AMI ID, to
      create the instance.
    * Options – The AWS CLI also provides choices that you can specify when executing operation. For example, you can
      use the --query option to limit the response text so that it returns only the instance ID of your new instan

<img src="img.png" alt="alt text" width="500" height="300">

* to list EC2 instances

```shell
aws ec2 describe-instances
```

* To run an EC2 instance with one line command

```shell
aws ec2 run-instances --image-id ami-0164f9b296f8e78cc --instance-type t4g.micro --count 1 --key-name Calvin_Key_Pair --security-group-ids sg-0ad8af9859c84d24d --subnet-id subnet-0983cbe1804161068 --block-device-mappings DeviceName=/dev/sdh,Ebs={VolumeSize=10}  --dry-run
```

* stop instance

```shell
aws ec2 stop-instances --instance-id i-123456
```

* Configure the aws region info

```shell
aws configure
```

* **AWS X-Ray :**
    * helps to track all actions.
    * helps developers analyze and debug production or distributed applications
    * X-Ray provides a complete view of requests as they travel through your application, and shows a map of your
      application’s underlying components.
    * Creates service map
        * This provides you with a view of connections among services in your application. The service map enables you
          to do the following:
            * Create a dependency tree
            * Detect latency or errors when working across AWS Availability Zones or AWS Regions
            * Identify services not operating as expecte
    * Will show you how long the process takes time
    * identify errors and bugs
        * X-Ray can automatically highlight bugs or errors in your application code by analyzing the response code for
          each request made to your application.
    * identify performance bottlenecks
        * With service maps, you can view relationships between services and resources in your application in real time.
          You can easily detect where high latencies are occurring and visualize node and edge latency distribution for
          services.
    * Build our own analysis and visualization app
        * X-Ray provides a set of query APIs you can use to build your own analysis and visualizations applications that
          use the data that X-Ray records
    * X-Ray Commands: https://docs.aws.amazon.com/xray/latest/api/API_Operations.html
    * Instromentantion for code
    * [Integration with other services](https://github.com/aws?q=xray-sdk.)

<img src="img.png" alt="alt text" width="500" height="300">

# Management Tools:

* **AWS CloudWatch**:
    * Monitor performance metrics/ analytic
    * Collects ant tracks metrics
    * Setup alarms
    * Create dashboards
    * Does not tell you one of instances getting down

<img src="./img/10.png" alt="alt text" width="500" height="300"></br>

<img src="img1.png" alt="alt text" width="500" height="300">

* Auto Scaling works as a trio of services working together. Elastic Load Balancing and EC2 instances feed metrics to
  Amazon CloudWatch. Auto Scaling defines a group with launch configurations and Auto Scaling policies. Amazon
  CloudWatch alarms run Auto Scaling policies to affect the size of your fleet. All of these services work well
  individually, but together they become more powerful and increase the control and flexibility that you demand

* **AWS CloudTrail:**
    * tells you who, when, what, which, where?
    * AWS CloudTrail is an AWS service that generates logs of calls to the AWS API. Because the AWS API underlies both
      the command line interface (AWS CLI) and the AWS Management Console, AWS CloudTrail can record all activity
      against the services it monitors
    * You can use the AWS API call history CloudTrail produces to track changes to AWS resources. These changes include
      creation, modification, and deletion of AWS resources, such as Amazon EC2 instances, Amazon VPC security groups,
      and Amazon EBS volumes.

<img src="img2.png" alt="alt text" width="500" height="300">

# Storage Services

<img src="./img/25.png" alt="alt text" width="500" height="300"></br>

* **Amazon Simple Storage Service Glacier (Amazon S3 Glacier)**
    * Low-cost storage service that provides highly secure, durable, and flexible storage for data archiving and online
      backup.
    * Data storing in Amazon S3 Glacier as archives. An archive can represent a single file, or you can combine several
      files to be uploaded as a single archive.

* **Amazon Elastic File System (Amazon EFS)**
    * Amazon EFS delivers a simple, scalable, elastic, highly available, and highly durable network file system as a
      service to Amazon Elastic Compute Cloud (Amazon EC2) instances.
    * Amazon EFS supports highly parallelized workloads. It is designed to meet the performance needs of big data and
      analytics, media processing, content management, web serving, and home directories
* **AWS Storage Gateway:**
    * AWS Storage Gateway connects an on-premises software appliance with cloud-based storage.
    * It provides seamless and secure storage integration between an organization’s on-premises IT environment and the
      AWS storage infrastructure, such as Amazon S3, Amazon S3 Glacier, and Amazon EBS.
    * AWS Storage Gateway use cases include the following:
        * Corporate file sharing
        * Enabling existing on-premises backup applications to store primary backups on Amazon S3
        * Disaster recovery
        * Mirroring data to cloud-based compute resources and then archiving it to Amazon S3 Glacier
* **Amazon Elastic Block Store (Amazon EBS):**
    * Amazon EBS volumes provide durable block-level storage for use with EC2 instances. Amazon EBS volumes are
      network-attached storage that persists independently from the running life of a single EC2 instanc

* Amazon S3 Bucket:
    * Amazon S3 provides developers and IT teams with highly secure, durable, and scalable object storage. Amazon S3 is
      easy to use, with a simple web service interface to store and retrieve any amount of data from anywhere on the web
    * use cases:
      <img src="./img/26.png" alt="alt text" width="500" height="300"></br>

    * Simple web page :
      <img src="./img/27.png" alt="alt text" width="500" height="300"></br>

    * Amazon S3 Concept:
        * Do not use (.) and (_) while giving name     
          <img src="./img/28.png" alt="alt text" width="500" height="300"></br>

    * Versioning is dissable in default, we should enable.
    * Predesigned Request: All objects and buckets are private by default.
        * Presigned URLs are useful if you want your user to be able upload a specific object to your bucket without
          being required to have AWS security credentials or permissions.
        * When you create a presigned URL, you must provide the following:
            * Your security credentials
            * Bucket name
            * Object key
            * HTTP method (PUT for uploading objects, GET for retrieving objects)
            * Expiration date and time The presigned URLs are valid only for the specified duration. Share the
              pre-signed URL with users who need to access your S3 bucket to put or retrieve objects

    * **Best Practices:**
        * Performance
            * Request
                * Handle NoSuchBucket Errors instead of checking of existing of fixed buckets.
                * Set the object metadata before uploading an object
                * Avoid using copy operation to update meta data
                * Cache bucket keys names if your app allows it.
            * Network Latency
                * Choose the bucket region closest
                * Compress data stored in Amazon s3
                * Use a content delivery network CDN, such as Amazon CloudFront to distrubute content with low-latency
                  and high data-transfer speeds
        * Data integrity
            * Ensure data is not corrupted in transit
            * Check the MD5 checksum of the object retrieved from the GET and PUT operation.

## Design NoSQL Solution with Amazon DynamoDB

<img src="./img/29.png" alt="alt text" width="500" height="300"></br>

* Comparing relational and noSql Db
    * Relational databases have the following characteristics:
        * Data is stored in tables that are related to each other through a primary key–foreign key relationship. The
          database supports complex queries and joins to retrieve a combination of data from various tables.
        * The schema of a relational database is defined in the beginning. Changes to the schema usually require a
          migration of data from the old schema to the new schema.
        * Data in SQL databases is queried using structured query language (SQL), which can allow for complex queries.
        * Relational databases support vertical scaling, which means that a single server must be made more powerful.
        * Relational databases support ACID transactions: atomicity, consistency, isolation, and durability.
        * Relational databases automatically support strong data consistency due to ACID properties of transactions.
    * Non-relational database. NoSQL databases have the following characteristics:
        * NoSQL databases can support wide-column stores, document stores, key-value stores, and graph stores. The type
          of data stored varies by NoSQL database.
        * NoSQL databases do not have a fixed schema. Different records can have different attributes.
        * Data in NoSQL databases is queried by focusing on collections of documents.
        * NoSQL databases support horizontal scaling. With this approach, you can partition and spread data across
          multiple cheaper servers instead of purchasing more powerful servers. For example, if a table stores
          information about 100,000 users, data can be partitioned to store a subset of 10,000 users on each server.
        * NoSQL databases generally deliver high performance with eventual consistency. Depending on the database, you
          can set it to strong consistency, if needed, for your usage scenario (
          example of strong consistency: read immediately after a write returns the latest data). Note: DynamoDB
          supports ACID via DynamoDB Transactions

<img src="./img/30.png" alt="alt text" width="500" height="300"></br>

* **Amazon Relational Database Service (Amazon RDS):** Provides relational database services in the cloud with support
  for the following database engines:
    * Amazon Aurora
    * PostgreSQL
    * MySQL
    * MariaDB
    * Oracle
    * Microsoft SQL Server

* **Amazon Redshift:** Fast, fully managed data warehouse
* **Amazon DynamoDB:** NoSQL database that supports both document and key-value store models
* **Amazon Neptune:** Fast, reliable, fully managed graph database service that makes it easy to build and run applications
  that work with highly connected datasets.
* **Amazon ElastiCache:** In-memory data cache that supports a fully managed Redis or Memcached engine
