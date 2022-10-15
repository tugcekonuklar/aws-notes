# Quiz IAM:

QUESTION 1

In AWS, what is IAM used for?

Choose 3

    * Creating and managing users and groups

    * Assigning permissions to allow and deny access to AWS resources

    * Managing access to AWS services

    Secure VPN access to AWS

Good work!

    Correct. IAM supports multiple methods to create and manage IAM users & IAM groups.
    
    Correct. Using policies, you can specify several layers of permission granularity.
    
    Correct. You can use AWS IAM to securely control individual and group access to your AWS resources.

QUESTION 2

True or False? AWS recommends that EC2 instances have credentials stored on them so that the instances can access other
resources (such as S3 buckets).

    True

    * False

Good work!

    AWS recommends IAM roles so that your applications can securely make API requests from your instances, without requiring you to manage the security credentials that the applications use.

QUESTION 3

Which is the best way to enable S3 read-access for an EC2 instance?

    Configure a bucket policy which grants read-access based on the EC2 instance name

    * Create an IAM role with read-access to S3 and assign the role to the EC2 instance

    Create a new IAM group and grant read access to S3. Store the group's credentials locally on the EC2 instance and configure your application to supply the credentials with each API request.
    
    Create a new IAM role and grant read-access to S3. Store the role's credentials locally on the EC2 instance and configure your application to supply the credentials with each API request

Good work!

    Correct. IAM roles allow applications to securely make API requests from instances, without requiring you to manage the security credentials that the applications use.

QUESTION 4

Which of the following can you use to test that an IAM policy attached to a user, group or role works as expected?

    IAM Access Analyzer

    Trusted Advisor

    * IAM Policy Simulator

    Lambda

Good work!

    You can use the IAM Policy Simulator test policies that are attached to IAM users, groups, or roles in your AWS account. If more than one policy is attached to the user, group, or role, you can test all the policies, or select individual policies to test. You can test which actions are allowed or denied by the selected policies for specific resources.

QUESTION 5

What is an IAM Policy?

    A file containing a user's private SSH key

    A CSV file which contains a users Access Key and Secret Access Key

    * A JSON document which defines one or more permissions
    
    The policy which determines how your AWS bill will be paid

Good work!

    Correct. An IAM policy is an object in AWS that, when associated with an identity or resource, defines their permissions. AWS evaluates these policies when an IAM principal (user or role) makes a request. Permissions in the policies determine whether the request is allowed or denied. Most policies are stored in AWS as JSON documents. AWS supports six types of policies: identity-based policies, resource-based policies, permissions boundaries, Organizations SCPs, ACLs, and session policies.

QUESTION 6

Which statement best describes IAM?

    IAM allows you to manage permissions for AWS resources only.
    
    * IAM allows you to manage users, groups, and roles and their corresponding level of access to the AWS Platform.
    
    IAM allows you to manage users' passwords only. AWS staff must create new users for your organization. This is done by raising a ticket.
    
    IAM stands for Improvised Application Management, and it allows you to deploy and manage applications in the AWS Cloud.

Good work!

    Correct. AWS Identity and Access Management (IAM) enables you to manage access to AWS services and resources securely. Using IAM, you can create and manage AWS users, groups, roles, and use permissions to allow and deny their access to AWS resources.

QUESTION 7

Which IAM entity can you use to delegate access to trusted entities such as IAM users, applications, or AWS services
such as EC2?

    IAM User

    IAM Group
    
    * IAM Role

    IAM Web Identity Federation

Good work!

    You can use IAM roles to delegate access to IAM users managed within your account, to IAM users under a different AWS account, to a web service offered by AWS such as Amazon Elastic Compute Cloud (Amazon EC2), or to an external user authenticated by an external identity provider (IdP) service that is compatible with SAML 2.0 or OpenID Connect, or a custom-built identity broker. IAM Roles.

# EC2

QUESTION 1

Which of the following EBS volume types gives you SAN performance in the cloud and is suitable for the largest, most
critical, high-performance applications?

    Throughput Optimized HDD (st1)
    
    Provisioned IOPS SSD (io2)

    * Provisioned IOPS SSD io2 Block Express

    General Purpose SSD (gp3)

Good work!

    Provisioned IOPS SSD io2 Block Express provides high performance, sub-millisecond latency SAN performance in the cloud.
    It is suitable for the largest, most critical, high-performance applications like Oracle, SAP HANA, Microsoft SQL
    Server, and SAS Analytics.. Each volume can support up to 64 TiB and 256,000 IOPS per volume.

QUESTION 2

You work for a media production company that streams popular TV shows to millions of users. They are migrating their web
application from an in house solution to AWS. They will have a fleet of over 10,000 web servers to meet the demand and
will need a reliable layer 4 load balancing solution capable of handling millions of requests per second. What AWS load
balancing solution would best suit their needs?

    Application Load Balancer.
    
    AWS Direct Connect.
    
    Elastic Load Balancer.

    * Network Load Balancer.

Good work!

    Correct. Network Load Balancer is best suited for load balancing of Transmission Control Protocol (TCP), User Datagram
    Protocol (UDP) and Transport Layer Security (TLS) traffic where extreme performance is required. Operating at the
    connection level (Layer 4), Network Load Balancer routes traffic to targets within Amazon Virtual Private Cloud (Amazon
    VPC) and is capable of handling millions of requests per second while maintaining ultra-low latencies.

QUESTION 3

You have a very popular blog site, which has recently had a surge in traffic. You want to implement an ElastiCache
solution to help take the load off the production database and you want to keep it as simple as possible. You will need
to scale your cache horizontally and object caching will be your primary goal. Which ElastiCache solution will best suit
your needs?

    Couchbase

    * Memcached
    
    Redis
    
    ArangoDB

Good work!

    Correct. The Memcached engine supports partitioning your data across multiple nodes. Because of this, Memcached clusters
    scale horizontally easily. For this scenario we do not require advanced data structure support, only object caching and
    horizontal scaling - so Redis is incorrect. Couchbase and ArangoDB are not supported by ElastiCache, so these are
    incorrect.

QUESTION 4

You run the internal intranet for a corporate bank. The intranet consists of a number of web servers and single
relational database running Microsoft SQL Server. Your peak demand occurs at 9am every week morning when users are first
logging in to the intranet. They can only log in using the company's internal network and it is not possible to access
the intranet from any location other than within the office building for security purposes. Management is considering a
change and to move this environment to AWS where users will be able to access the intranet via a software VPN. You have
been asked to evaluate a migration to AWS and to identify the best EC2 billing model for your company's intranet. You
must keep costs low and to be able to scale at particular times of day. You must maintain availability of the intranet
throughout office hours. Management do not want to be locked into any contracts in case for some reason they want to go
back to hosting internally. What EC2 billing model should you recommend?

    Reserved Instances.
    
    Dedicated Instances.

    * On-demand.

    Spot Instances.

Good work!

    Correct. On-Demand Instances let you pay for compute capacity by the hour or second (minimum of 60 seconds) with no
    long-term commitments. On-demand instances satisfy the requirements of: low cost, availability during office hours and
    no lock in contracts.
    Dedicated instances are more costly, Reserved instances are a long term (1 to 3 year) commitment, and spot instances may
    terminate at any time so do not meet the availability requirements.

QUESTION 5

You work for an online gaming store which has a global worldwide leader board for players of the game. You need to
implement a caching system for your leader board that has multiple availability zones in order to prevent an outage.
Which ElastiCache solution should you use?

    * Redis

    Couchbase
    
    Memcached
    
    ArangoDB

Good work!

    Correct. Amazon ElastiCache for Redis supports both Redis cluster and non-cluster modes and provides high availability
    via support for automatic failover by detecting primary node failures and promoting a replica to be primary with minimal
    impact. It allows for read availability for your application by supporting read replicas (across availability zones), to
    enable the reads to be served when the primary is busy with the increased workload.

QUESTION 6

You are the IT manager at a furniture retailer and they are considering moving their web application to AWS. They
currently colocate their servers in a co-location facility and the contract for this facility is now coming to an end.
Management are comfortable signing a 3 year contract and want to get the cheapest web servers as possible while still
maintaining availability. Their traffic is very steady and predictable. What EC2 pricing model would you recommend to
maintain availability and to get the lowest cost price available?

    On-demand.
    
    Spot Instances.
    
    Dedicated Instances.

    * Reserved Instances.

Good work!

    Correct. A Reserved Instance (RI) is an EC2 offering that provides you with a significant discount on EC2 usage when you
    commit to a one-year or three-year term.

QUESTION 7

You have a three-tier web application with a web server tier, application tier, and database tier. The application is
spread across multiple availability zones for redundancy and is in an Auto Scaling group with a minimum size of two and
a maximum size of ten. The application relies on connecting to an RDS Multi-AZ database. When new instances are
launched, they download a connection string file that is saved in an encrypted S3 bucket using a bootstrap script.
During a routine scaling event, you notice that your new web servers are failing their health checks and are not coming
into service. You investigate and discover that the web server's S3 read-only role has no policies attached to it. What
combination of steps should you take to remediate this problem while maintaining the principle of least privilege?

Choose 2

    Attach the S3 – Administrator policy.
    
    Copy the role to a new AMI.
    
    Create a snapshot of the EBS volume and then restart the instance.
    
    Create a new role giving Lambda permission to execute.

    * Leave the healthy instances as they are and allow new instances to come into service after fixing the policy issue.
    
    * Attach the S3 – read-only policy to the role.

Good work!

    New instances can download a connection string, provided that the read-only policy is attached to the role. Instances
    will not download the connection string file without the S3 policy since it is required to allow the bootstrapping
    process to complete successfully.
    
    The read-only policy attached to the role will solve the permission issue and is in line with the principle of least
    privilege.

QUESTION 8

Individual EC2 instances are provisioned ____.

    * In Availability Zones
    In Regions
    Globally
    To a user

Good work!

    Correct. When provisioning an instance you must choose which Availability Zone the instance will belong to.

QUESTION 9

You have an EC2 instance in a single availability zone connected to an RDS instance. The EC2 instance needs to
communicate to S3 to download some important configuration files from it. You try the command aws s3 cp s3://yourbucket
/var/www/html however you receive an error message. You log in to Identity Access Management (IAM) and discover there is
no role created to allow EC2 to communicate to S3. You create the role and attach it to the existing EC2 instance. How
fast will the changes take to propagate?

    The same duration as CloudWatch detailed monitoring – 1 minute.
    
    It depends on the region and availability zone.

    * Almost immediately.

    The same duration as CloudWatch standard monitoring – 5 minutes.

Good work!

    Correct. You can change the permissions on the IAM role associated with a running instance, and the updated permissions
    take effect almost immediately.

QUESTION 10

In order to enable encryption at rest using EC2 and Elastic Block Store, you must ____.

    Mount the EBS volume into S3 and then encrypt the bucket using a bucket policy.
    
    Configure encryption using the appropriate Operating Systems file system
    
    Configure encryption using X.509 certificates

    * Configure encryption when creating the EBS volume

Good work!

    Correct. When you create a new, empty EBS volume, you can encrypt it by enabling encryption for the specific volume
    creation operation.

QUESTION 11

You work for a web analytics firm who have recently migrated their application to AWS. The application sits behind an
Elastic Load Balancer and it monitors user traffic to their website. You have noticed that in the application logs you
are no longer seeing your users public IP addresses, instead you are seeing the private IP address of the elastic load
balancer. This data is critical for your business and you need to rectify the issue immediately. What should you do?

    Migrate the application in front of a Network Load Balancer and then reverse proxy traffic to your RDS instance.
    
    Migrate the application to AWS Lambda instead of EC2 and put the Lambda function behind a Network Load Balancer.

    * Update the application to log the x-forwarded-for header to get your users public IPv4 addresses.

    Install a CloudWatch logs agent on the EC2 instances behind the Elastic Load Balancer to monitor the public IPv4
    addresses and then stream this data to AWS Neptune.

Good work!

    Correct. Your access logs capture the IP address of your load balancer because the load balancer establishes the
    connection to your instances. You must perform additional configuration to capture the IP addresses of clients in your
    access logs. For Application Load Balancers and Classic Load Balancers with HTTP/HTTPS listeners, you must use
    X-Forwarded-For headers to capture client IP addresses. Then, you must print those client IP addresses in your access
    logs.
    Reference: [How do I capture client IP addresses in my ELB access logs?](https://aws.amazon.com/tr/premiumsupport/knowledge-center/elb-capture-client-ip-addresses/)

QUESTION 12

Which of the following services can be used to securely store confidential information like credentials and license
codes so that they can be accessed by EC2 instances?

    DynamoDB
    * Systems Manager Parameter Store
    KMS
    IAM

Good work!

    AWS Systems Manager Parameter Store provides secure, hierarchical storage for configuration data management and secrets
    management. You can store data such as passwords, database strings, and license codes as parameter values.

QUESTION 13

You have a WordPress site hosted on EC2 with a MySQL database hosted on RDS. The majority of your traffic is read
traffic. There is only write traffic when you create a new blog. One of your blogs has gone viral and your WordPress
site is struggling to cope. You check your CloudWatch metrics and notice your RDS instance is at 100% CPU utilization.
What two steps should you take to reduce the CPU utilization?

Choose 2

    Migrate from an Elastic Load Balancer to a Network Load Balancer so you can sustain more connections.
    
    Enable Multi-AZ on your RDS instances and point multiple EC2 instances to the new Multi-AZ instances, thereby spreading
    the load.

    * Create an ElastiCache cluster and use this to cache your most frequently read blog posts.
    * Create multiple RDS read replicas and point multiple EC2 instances to these read replicas, thereby spreading the load.

Good work!

    Correct. Amazon ElastiCache improves the performance of web applications by allowing you to retrieve information from a
    fast, managed, in-memory system, instead of relying entirely on slower disk-based databases.
    
    Correct. Amazon RDS Read Replicas make it easy to elastically scale out beyond the capacity constraints of a single DB
    instance for read-heavy database workloads.

QUESTION 14

You are a developer for a genomics firm that is moving its infrastructure to AWS. Their environment consists of a
three-tier web application, a web tier, an application tier and a relational database tier. They have a separate fleet
of virtual machines that are used to access large HPC clusters on the fly. Their lab researchers run multiple projects
simultaneously and they will need to launch and decommission 1,000's of nodes on-demand while reducing the time required
to complete genomic sequencing from weeks to days. In order to stay competitive they need to do this at as low cost as
possible, with no long-term contracts. These HPC clusters can run any time day or night and their workloads store
information in S3, so the instances can be terminated at any time without any effect on the data. What is the most COST
EFFECTIVE EC2 pricing model for their requirements?

    Reserved Instances.
    
    On-demand Instances.
    
    Dedicated Instances.

    * Spot Instances.

Good work!

    Correct. Amazon EC2 Spot Instances let you take advantage of unused EC2 capacity in the AWS cloud and are the lowest
    cost option for on-demand and short term capacity requirements. As the HPC cluster nodes store the data in S3 the
    termination of Spot instances will not impact the data processing. Both on-demand and dedicated instances are more
    expensive than Spot instances, and reserved instances are for long running applications (1 to 3 years) so are not
    suitable for this HPC cluster scenario.

QUESTION 15

You see a "timed out" error when using the AWS CLI to list all the files in an S3 bucket containing thousands of files.
What could be the reason for this?

    Your network connection is too slow.
    
    You have not installed the AWS CLI correctly.

    * Too many results are being returned which is causing the command to time out.

    You don't have the correct permission to run the command.

Good work!

    Using the AWS CLI to list all the files in an S3 bucket containing thousands of files can cause your API call to exceed
    the maximum allowed time for the AWS CLI, and generate a "timed out" error. To avoid this, you can use the --page-size
    option to specify that the AWS CLI request a smaller number of items from each call to the AWS service.

QUESTION 16

    A new CIO joins your company and implements a new company policy that all EC2 EBS backed instances must have encryption
    at rest. What is the quickest and easiest way to apply this policy to your existing EC2 EBS backed instances?
    
    In the AWS console, click on the EC2 instances, click actions and click encrypt EBS volumes.
    
    Create an encrypted snapshot of the EC2 volume using the encrypt-on-the-fly option. Create an AMI of the copied snapshot
    and then redeploy the EC2 instance using the encrypted AMI. Delete the old EC2 instance.
    
    Create an encrypted AMI of the EC2 volume using Windows BitLocker.

    * Create a snapshot of the EC2 volume. Then create a copy of the snapshot, checking the box to enable encryption. Create an AMI of the copied snapshot and then redeploy the EC2 instance using the encrypted AMI. Delete the old EC2 instance.

Good work!

    Correct. Although there is no direct way to encrypt an existing unencrypted volume or snapshot, you can encrypt them by
    creating either a volume or a snapshot.

QUESTION 17

You work for a government contractor who supply services that are critical to national security. Because of this your
corporate IT policy states that no multi-tenant virtualization is authorized within the company. Despite this, they are
interested in moving to AWS, but they cannot violate corporate IT policy. Which EC2 billing model would you recommend
that they use to achieve this?

    Reserved Instances.
    
    On-demand.
    
    Spot Instances.

    * Dedicated Instances.

Good work!

    Correct. Dedicated instances run on its own dedicated hardware, solely belonging to that customer, and they do not share
    resources.

QUESTION 18

Which of the following are valid types of Elastic Load Balancers?

Choose 3

    Virtual Load Balancer.
    * Network Load Balancer.
    * Classic Load Balancer.
    * Application Load Balancer.

Good work!

    Correct. Elastic Load Balancing offers three types of load balancers: Application Load Balancer, Network Load Balancer,
    and Classic Load Balancer.

# S3

QUESTION 1

Which of the following options allows users to have secure access to private files located in S3?

Choose 3

    * CloudFront Signed URLs


    * CloudFront Signed Cookies


    * CloudFront Origin Access Identity


    Public S3 buckets

Good work!

    There are three options in the question which can be used to secure access to files stored in S3 and therefore can be considered correct. Signed URLs and Signed Cookies are different ways to ensure that users attempting access to files in an S3 bucket can be authorized. One method generates URLs and the other generates special cookies but they both require the creation of an application and policy to generate and control these items. An Origin Access Identity on the other hand, is a virtual user identity that is used to give the CloudFront distribution permission to fetch a private object from an S3 bucket. Public S3 buckets should never be used unless you are using the bucket to host a public website and therefore this is an incorrect option.

QUESTION 2

You are hosting a website in an Amazon S3 bucket. Which feature defines a way for client web applications that are
loaded in one domain to interact with resources in a different domain?

    Bucket ACL
    
    
    IAM Role
    
    
    Bucket Policy
    

    * CORS

Good work!

    Cross-origin resource sharing (CORS) defines a way for client web applications that are loaded in one domain to interact with resources in a different domain. With CORS support, you can build rich client-side web applications with Amazon S3 and selectively allow cross-origin access to your Amazon S3 resources. Reference: Configuring and using cross-origin resource sharing (CORS).

QUESTION 3

You are hosting a static website in an S3 bucket that uses Javascript to reference assets in another S3 bucket. For some
reason, these assets are not displaying when users browse to the site. What could be the problem?

    You cannot use one S3 bucket to reference another S3 bucket.
    
    
    Amazon S3 does not support Javascript.
    
    
    You need to open port 80 on the appropriate security group in which the S3 bucket is located.


    * You haven't enabled Cross-origin Resource Sharing (CORS) on the bucket where the assets are stored.

Good work!

QUESTION 4

The total volume of data and number of objects you can store in Amazon S3 are unlimited.

    False

    * True

Good work!

    The total volume of data and number of objects you can store in Amazon S3 are unlimited. Individual Amazon S3 objects can range in size from a minimum of 0 bytes to a maximum of 5 terabytes. The largest object that can be uploaded in a single PUT is 5 gigabytes. For objects larger than 100 megabytes, customers should consider using the Multipart Upload capability. Amazon S3 FAQs.

QUESTION 5

Which storage class is suitable for long-term archiving of data that occasionally needs to be accessed within a few
hours or minutes?

    S3 Standard

    S3 Glacier Deep Archive

    *  S3 Glacier

    S3 Intelligent-Tiering

Good work!

    S3 Glacier is designed for long-term data archiving that occasionally needs to be accessed within a few hours or minutes. It supports retrieval options of 1 minute to 12 hours.

QUESTION 6

When you first create an S3 bucket, this bucket is publicly accessible by default.

    True

    * False

Good work!

QUESTION 7

You are using S3 in ap-northeast-1 to host a static website in a bucket called "acloudguru". What would the new URL
endpoint be?

    http://www.acloudguru.s3-website-ap-northeast-1.amazonaws.com


    * http://acloudguru.s3-website-ap-northeast-1.amazonaws.com


    https://s3-ap-northeast-1.amazonaws.com/acloudguru/
    
    
    http://acloudguru.s3-website-ap-southeast-1.amazonaws.com

Good work!

    Depending on your Region, your Amazon S3 website endpoint follows one of these two formats:
    
    s3-website dash (-) Region ‐ http://bucket-name.s3-website-Region.amazonaws.com
    s3-website dot (.) Region ‐ http://bucket-name.s3-website.Region.amazonaws.com
    The Asia Pacific (Tokyo) region ap-northeast-1 uses the website endpoint s3-website-ap-northeast-1.amazonaws.com.
    
    Hence, the correct URL is http://acloudguru.s3-website-ap-northeast-1.amazonaws.com.
    
    References:
    
    Website endpoints
    Amazon S3 Website Endpoints

QUESTION 8

Which of the following encryption methods are supported in S3?
Choose 3

    * SSE-S3

    SSE-AES

    * SSE-C

    * SSE-KMS

Good work!

    Server-side encryption is the encryption of data at its destination by the application or service that receives it. Amazon S3 encrypts your data at the object level as it writes it to disks in its data centers and decrypts it for you when you access it. You have three mutually exclusive options, depending on how you choose to manage the encryption keys: Server-Side Encryption with Amazon S3-Managed Keys (SSE-S3), Server-Side Encryption with Customer Master Keys (CMKs) Stored in AWS Key Management Service (SSE-KMS), or Server-Side Encryption with Customer-Provided Keys (SSE-C). Reference: Protecting data using server-side encryption.

QUESTION 9

True or False? An Amazon S3 object owner can optionally share objects with others by creating a presigned URL.

    False

    * True

Good work!

    All Amazon S3 objects by default are private. Only the object owner has permission to access these objects. However, the object owner can optionally share objects with others by creating a presigned URL, using their own security credentials, to grant time-limited permission to download the objects. Sharing an object with a presigned URL.

QUESTION 10

You would like to configure your S3 bucket to only serve content over HTTPS/SSL and explicitly deny all unencrypted HTTP
access. In your bucket policy, how should you specify the type of request that should be denied?

```json
{
  "Id": "ExamplePolicy",
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "AllowSSLRequestsOnly",
      "Action": "s3:*",
      "Effect": "Deny",
      "Resource": [
        "arn:aws:s3:::DOC-EXAMPLE-BUCKET",
        "arn:aws:s3:::DOC-EXAMPLE-BUCKET/*"
      ],
      "Condition": {
        "Bool": {
          "aws:SecureTransport": "false"
        }
      },
      "Principal": "*"
    }
  ]
}
```

Good work!

    Explicitly denying requests that are identified as "aws:SecureTransport": "false" would deny requests that are using HTTP and are unencrypted. AWS Documentation: What S3 bucket policy should I use to comply with the AWS Config rule s3-bucket-ssl-requests-only?

QUESTION 11

You would like to configure your S3 bucket to deny put object requests that do not use server-side encryption. Which
bucket policy can you use to deny permissions to upload objects, unless the request includes server-side encryption?

```json
 {
  "Version": "2012-10-17",
  "Id": "PutObjPolicy",
  "Statement": [
    {
      "Sid": "DenyUnEncryptedObjectUploads",
      "Effect": "Deny",
      "Principal": "*",
      "Action": "s3:PutObject",
      "Resource": "arn:aws:s3:::bucket/*",
      "Condition": {
        "Null": {
          "s3:x-amz-server-side-encryption": "true"
        }
      }
    }
  ]
}

```

Good Work!

    The condition above looks for a Null value for the s3:x-amz-server-side-encryption key. If this condition is true, it means the request is Null and does not include server-side encryption. Setting the condition in the condition policy to "s3:x-amz-server-side-encryption": "true" with "Effect": "Deny" and "Action": "s3:PutObject" would deny put object requests that do not use server-side encryption. AWS Documentation: How to Prevent Uploads of Unencrypted Objects to Amazon S3.

QUESTION 12

What is the HTTP code you would see once you successfully place a file in an S3 bucket?

    404
    
    524

    * 200

    312

Good work!

QUESTION 13

What is the largest size file you can transfer to S3 using a single PUT operation?

    1GB
    
    5TB
    
    100MB

    * 5GB

Good Work !

    Individual Amazon S3 objects can range in size from a minimum of 0 bytes to a maximum of 5 terabytes. The largest object that can be uploaded in a single PUT is 5 gigabytes. For objects larger than 100 megabytes, customers should consider using the Multipart Upload capability.

QUESTION 14

Which of the following HTTP methods supported by CloudFront are read-only methods?
Choose 3

    * OPTIONS

    PATCH

    POST

    * GET

    DELETE

    * HEAD

Good work!

    'OPTIONS is used to find out what other HTTP methods are supported by the given URL.'
    The GET method is used to read data.
    HEAD is used to inspect resource headers; similar to GET, except without the response body.

QUESTION 15

Which storage class is suitable for long-term archiving of data and supports millisecond retrieval times?

    * Glacier Instant Retrieval


    Glacier Flexible Retrieval
    
    
    S3 Standard-Infrequent Access


    Glacier Deep Archive

Good work!

    Glacier Instant Retrieval is designed for long-lived data, accessed approximately once per quarter with millisecond retrieval time. 

QUESTION 16

You would like to migrate your website to AWS and use CloudFront to provide the best performance. Your users will need
to complete a form on the website in order to subscribe to a mailing list and comment on blog posts. Which of the
following allowed HTTP methods should you configure in your CloudFront distribution settings?

    * GET, HEAD, OPTIONS, PUT, POST, PATCH, DELETE

    GET, HEAD

    GET, HEAD, OPTIONS, POST
    
    GET, HEAD, OPTIONS

Good work!

    This combination of HTTP methods will enable your users to interact with the website and send, modify, insert, and delete data.

# Serverless

QUESTION 1

How does API Gateway help to deal with legacy SOAP applications?

Choose 2

    * Converts the response from the application to JSON
    
    
    Converts the response from the application to HTML
    
    
    * Provides web service passthrough for SOAP applications
    
    
    Converts the response from the application to XML

Good work!

    If your existing services return XML-style data, you can use the API Gateway to transform the output to JSON as part of your modernization effort.

    References:
    
    [Enhancing Legacy Services](https://aws.amazon.com/tr/blogs/aws/amazon-api-gateway-build-and-run-scalable-application-backends/)
    [API Gateway guide to SOAP](https://gist.github.com/buger/e94be691cf17e73b2a8003c4887bfd12)
    
    When a method request carries a payload and either the Content-Type header does not match any specified mapping template or no mapping template is defined, you can choose to pass the client-supplied request payload through the integration request to the backend without transformation. The process is known as integration passthrough.
    
    References:
    
    [Integration passthrough behaviors](https://docs.aws.amazon.com/apigateway/latest/developerguide/integration-passthrough-behaviors.html)
    [How to configure Amazon API Gateway as a SOAP webservice passthrough in minutes](https://www.rubix.nl/blogs/how-configure-amazon-api-gateway-soap-webservice-passthrough-minutes/)
    [API Gateway guide to SOAP](https://gist.github.com/buger/e94be691cf17e73b2a8003c4887bfd12)

QUESTION 2

Your application relies on a number of Lambda functions. During testing, you would like to make sure you are always
using the latest version of the function. How can you ensure that your application always launches the very latest
version of your code?

    * Reference the function using the $LATEST suffix.
    
    
    Publish a new version of your function based on the specific version of code that you would like to use.
    
    
    Create an alias and reference the function using the alias.
    
    
    Create a qualified ARN which points to the specific version of code that you would like to use.

Good work!

    When you create a Lambda function, there is only one version—the $LATEST version. You can use either the qualified or unqualified ARN in your event source mapping to invoke the $LATEST version. If you always want to use the latest version of code, avoid using your own alias or any specific Lambda version as these will not be updated when new code is uploaded to Lambda.

QUESTION 3

You have an internal API that you use for your corporate network. Your company has decided to go all in on AWS to reduce
their data center footprint. They will need to leverage their existing API within AWS. What is the most efficient way to
do this.

    Use AWS API Import/Export feature of AWS Storage Gateway.
    
    
    * Use an OpenAPI definition file to import your API in to API Gateway.
    
    
    Replicate your API to API Gateway using the API Replication Master.
    
    
    Recreate the API manually.

Good work!

    Correct. You can use API Gateway to import a REST API from an external definition file into API Gateway. Currently, API Gateway supports OpenAPI v2.0 and OpenAPI v3.0 definition files. You can update an API by overwriting it with a new definition, or you can merge a definition with an existing API. You specify the options by using a mode query parameter in the request URL.

    Reference: Configuring a REST API using OpenAPI(https://docs.aws.amazon.com/apigateway/latest/developerguide/api-gateway-import-api.html)

QUESTION 4

You have launched a new web application on AWS using API Gateway, Lambda, and S3. Someone posts a thread on Reddit about
your application and it goes viral. You start receiving 10,000 requests every second, and you notice that most types of
requests are similar. Because of this, your web application begins to struggle. What can you do to optimize your
application performance?

    Change your Route 53 alias record to point to AWS Neptune. Configure Neptune to filter your API requests to genuine requests only.
    
    
    Enable API Gateway Accelerator.
    
    
    Migrate your API Gateway to a Network Load Balancer and enable session stickiness for all sessions.
    
    
    * Enable API Gateway caching to cache frequent requests.

Good work!

    Since these requests are similar, you can enable API caching in Amazon API Gateway to cache your endpoint's responses. With caching, you can reduce the number of calls made to your endpoint and also improve the latency of requests to your API.

QUESTION 5

You have created a serverless application which converts text into speech using a combination of S3, API Gateway,
Lambda, Polly, DynamoDB and SNS. Your users complain that only some text is being converted, whereas longer amounts of
text do not get converted. What could be the cause of this problem?

    AWS X-Ray service is interfering with the application and should be disabled.
    
    
    * Your Lambda function needs a longer execution time. You should check how long is needed in the fringe cases and increase the timeout inside the function to slightly longer than that.
    
    
    Polly has built-in censorship, so if you try and send it text that is deemed offensive, it will not generate an MP3.
    
    
    You’ve placed your DynamoDB table in a single availability zone which is currently down, causing an outage.

Good work!

    Correct. To fix Lambda timeout issues, review the logs of the API call to find the problem. Then, change the timeout settings as needed.

QUESTION 6

Which of the following Step Functions workflows can be used to orchestrate a long-running workflow that could take up to
a year to complete?

    * Standard Workflow
    
    
    Asynchronous Express Workflow
    
    
    Synchronous Express Workflow
    
    
    Express Workflow

Good work!

    A Standard Workflow can be used for long-running workflows (up to 1 year) that run at-most-once and are non-idempotent.

QUESTION 7

Which of the following Step Functions workflows should be used when you need to orchestrate a short process that
normally takes 2 minutes to complete, and you require the result of the workflow to be returned after it has completed?

    * Synchronous Express Workflow
    
    
    Express Workflow
    
    
    Asynchronous Express Workflow
    
    
    Standard Workflow

Good work!

    Synchronous Express Workflows return the result of the workflow after it has completed. They are designed to be used for situations where a workflow must complete before the next step begins (e.g., confirm successful payment before sending an order).

QUESTION 8

Your web application is running on Lambda, API Gateway, DynamoDB and S3 and you have recently seen a significant
increase in traffic to your website. The application support team are now reporting that Lambda invocations are being
rejected with a 429 HTTP status code. What is the most likely cause of this issue that you would check first?

    [Correct] You have reached the default concurrent executions limit for Lambda.
    
    
    You have reached the default concurrent requests limit for DynamoDB.
    
    
    You have reached the default concurrent requests limit for S3.
    
    
    You have reached the default concurrent requests limit for API Gateway.

Sorry!

    Since your Lambda invocations are being rejected with a 429 HTTP status code and the quota of API Gateway requests per second is much higher than the default quota of Lambda concurrent executions, you first need to check the ConcurrentExecutions metrics for your function in the AWS Region where you see throttling. A service quota increase request can be submitted to AWS once the root cause of the issue is confirmed.

Correct Answer

    AWS Lambda limits the amount of compute and storage resources that you can use to run and store functions, including a Concurrent Executions limit, which is set to 1000 per region, by default. To request an increase, use the Support Center console.

QUESTION 9

You have created a simple serverless website using S3, Lambda, API Gateway and DynamoDB. Your website will process the
contact details of your customers, predict an expected delivery date of their order and store their order in DynamoDB.
You test the website before deploying it in to production and you notice that although the page executes, and the lambda
function is triggered, it is unable to write to DynamoDB. What could be the cause of this issue?

    The availability zone that Lambda is hosted in is down.
    
    
    You have written your function in Python which is not supported as a run time environment for Lambda.
    
    
    The availability zone that DynamoDB is hosted in is down.
    
    
    * Your lambda function does not have the sufficient Identity Access Management (IAM) permissions to write to DynamoDB.

Good work!

    Correct. A Lambda function also has a policy, called an execution role, that grants it permission to access AWS services and resources. It needs permission to write to DynamoDB in this case.

QUESTION 10

You are developing a new application using serverless infrastructure and are using services such as S3, DynamoDB,
Lambda, API Gateway, CloudFront, CloudFormation and Polly. You deploy your application to production and your end users
begin complaining about receiving a HTTP 429 error. What could be the cause of the error?

    * You enabled API throttling for a rate limit of 1000 requests per second while in development and now that you have deployed to production your API Gateway is being throttled.
    
    
    You have an S3 bucket policy which is preventing Lambda from being able to write files to your bucket, generating a HTTP 429 error.
    
    
    Your lambda function does not have sufficient permissions to read to DynamoDB and this is generating a HTTP 429 error.
    
    
    Your CloudFormation stack is not valid and is failing to deploy properly which is causing a HTTP 429 error.

Good work!

    Correct. When request submissions exceed the steady-state request rate and burst limits, API Gateway fails the limit-exceeding requests and returns 429 Too Many Requests error responses to the client. Upon catching such exceptions, the client can resubmit the failed requests in a way that is rate limiting, while complying with the API Gateway throttling limits.

QUESTION 11

You would like to use X-Ray to monitor your application which runs on a number of Docker containers. Where should you
deploy and run the X-Ray daemon?

    * Use a dedicated Docker container build from an image which includes the X-Ray daemon.
    
    
    Install the X-Ray daemon on the underlying EC2 instance.
    
    
    The X-Ray daemon will already be installed on the underlying EC2 instance by default.
    
    
    Install the X-Ray daemon on Lambda.

Good work!

    X-Ray provides a Docker container image that you can deploy alongside your application. For custom configurations, you may need to define your own Docker image.

QUESTION 12

Which of the following services does X-Ray integrate with?

Choose 4

    * Amazon S3
    
    
    Amazon CloudFront
    
    
    * Elastic Load Balancer
    
    
    Amazon Elastic File System (EFS)
    
    
    * AWS Lambda
    
    
    * Amazon Elastic Block Store (EBS)

API Gateway

Good work!

    AWS X-Ray integrates with Amazon S3 to trace upstream requests to update your application's S3 buckets. If a service traces requests by using the X-Ray SDK, Amazon S3 can send the tracing headers to downstream event subscribers such as AWS Lambda, Amazon SQS, and Amazon SNS. X-Ray enables trace messages for Amazon S3 event notifications. Reference: Amazon S3 and AWS X-Ray.
    
    The following services provide X-Ray integration: AWS Lambda, Amazon API Gateway, Elastic Load Balancing, AWS Elastic Beanstalk, Amazon Simple Notification Service, and Amazon Simple Queue Service. Reference: AWS X-Ray Supported AWS Services.

QUESTION 13

You are trying to configure X-Ray to monitor Java applications running on your EC2 instances. Which of the following
will be required in order to get X-Ray working?

Choose 2

    You will need to restart your application.
    
    
    * The X-Ray daemon will need to be installed and running on your EC2 instances.
    
    
    You will need to install the CloudWatch agent.
    
    
    You will need to restart your instance.
    
    
    * Use X-Ray SDK for Java to generate and send trace data to the X-Ray daemon.

Good work!

    Both the X-Ray SDK and X-Ray Daemon, and you need to Instrument your application. Your application will need to be deployed with the additional code, specifying the details you want AWS X-Ray to capture. This is done using the X-Ray SDK, which provides a programmatic interface for your application to send information to the X-Ray Daemon. Once the X-Ray Daemon has received the information, it will send the information to AWS X-Ray to be reviewed. This requires both the X-Ray SDK and X-Ray Daemon to be installed. You will not need to restart your instance, since any additional IAM Roles can be added without shutting down the instance. You may not need to restart your application, depending on its architecture. CloudWatch is a separate service, and it's agent is not required for X-Ray.

QUESTION 14

You work for a gaming company that has built a serverless application on AWS using Lambda, API Gateway and DynamoDB.
They release a new version of the Lambda function and the application stops working. You need to get the application up
and back online as fast as possible. What should you do?

    DynamoDB is not serverless and is causing the error. Migrate your database to RDS and redeploy the lambda function.
    
    
    Create a CloudFormation template of the environment. Deploy this template to a separate region and then redirect Route 53 to the new region.
    
    
    * Roll your Lambda function back to the previous version.
    
    
    The new function has some dependencies not available to Lambda. Redeploy the application on EC2 and put the EC2 instances behind a network load balancer.

Good work!

    Correct. You can use versions to manage the deployment of your Lambda functions.

QUESTION 15

You have created an application using serverless architecture using Lambda, Api Gateway, S3 and DynamoDB. Your boss asks
you to do a major upgrade to API Gateway and you do this and deploy it to production. Unfortunately something has gone
wrong and now your application is offline. What should you do to bring your application up as quickly as possible?

    Delete the existing API Gateway.
    
    
    Restore your previous API gateway configuration using an EBS snapshot.
    
    
    Restart API Gateway for the new changes to take effect.
    
    
    * Rollback your API Gateway to the previous stage.

Good work!

    Correct. You can easily restore your AWS API Gateway from a previous deployment by selecting a stage that has the last version of your deployment.

QUESTION 8

You are a developer for a busy real estate company, and you want to enable other real estate agents to have the ability
to show properties on your books, but skinned so that it looks like their own website. You decide the most efficient way
to do this is to expose your API to the public using API Gateway. The project works well, but one of your competitors
starts abusing this, sending your API tens of thousands of requests per second. This generates an HTTP 429 error. Each
agent connects to your API using individual API keys. What actions can you take to stop this behavior?

    Deploy multiple API Gateways and give the agent access to another API Gateway.
    
    
    * Throttle the agent's API access using the individual API Keys
    
    
    Use AWS Shield Advanced API protection to block the requests.
    
    
    Place an AWS Web Application Firewall in front of API Gateway and filter the requests.

Good work!

    To prevent your API from being overwhelmed by too many requests, Amazon API Gateway throttles requests to your API using the token bucket algorithm, where a token counts for a request. You can enable usage plans to restrict client request submissions to within specified request rates and quotas. This restricts the overall request submissions so that they don't go significantly past the account-level throttling limits in a Region. Amazon API Gateway provides Per-client throttling limits that are applied to clients that use API keys associated with your usage policy as client identifier.

QUESTION 15

You have designed a serverless learning management system and you are ready to deploy your code into a test/dev
environment. The system uses a combination of Lambda, API Gateway, S3 and CloudFront and is designed to be highly
available, fault-tolerant and scalable. What are the three different ways you can deploy your code to Lambda?

Choose 3

    * Zip your code into a zip file and upload it via the Lambda console.
    
    
    * Copy and paste your code in to the integrated development environment (IDE) inside Lambda.
    
    
    Import your code to Amazon’s Glacier and change your Lambda execution handler to point to Glacier.
    
    
    Upload your code to S3 and use a MySQL connection string to connect Lambda to your S3 bucket.
    
    
    * Write a CloudFormation template that will deploy your environment including your code.

Good work!

    Correct. A deployment package is a ZIP archive that contains your function code and dependencies. You can upload the package directly to Lambda, or you can use an Amazon S3 bucket, and then upload it to Lambda. If the deployment package is larger than 50 MB, you must use Amazon S3.
    
    Correct. The code editor in the AWS Lambda console enables you to write, test, and view the execution results of your Lambda function code.
    
    Correct. The CloudFormation AWS::Lambda::Function resource creates a Lambda function. To create a function, you need a deployment package and an execution role.

# DynamoDb

QUESTION 1

Which DynamoDB feature can be used to define an expiry date and time for a data record in your table?

    DynamoDB Streams

    * TTL

    Exponential Backoff

    DynamoDB Expiry

Good work!

    TTL or Time To Live is used to set an expiry time on your record

QUESTION 2

You have an application that needs to read 25 items per second and each item is 13KB in size. Your application uses
strongly consistent reads. What should you set the read throughput to?

    25

    50

    10

    * 100

Good work!

    Each Read Capacity unit represents 1 x 4KB Strongly Consistent Read. 13 / 4 = 3.25 rounded up to 4KB multiply by 25 = 100.

QUESTION 3

In order to address performance considerations and achieve faster response times, which of the following best practices
can be used for Querying and Scanning Data in Amazon DynamoDB large tables?

Choose 2

    * Run parallel scans if the table size is 20 GB or larger, the table's provisioned read throughput is not being fully used, and sequential Scan operations are too slow.
    
    
    Set your queries to be eventually consistent.
    
    
    Scan using the 'FilterExpression' parameter to discard items that you do not want to appear in the results.
    
    
    * Reduce the page size to return fewer items per results page.

Sorry!

    A Query operation performs eventually consistent reads, by default.

Correct Answer

      For large tables, a parallel scan can complete much faster than a sequential one, if the table size is 20 GB or larger, the table's provisioned read throughput is not being fully used, and sequential Scan operations are too slow. Reference: Best Practices for Querying and Scanning Data.
    A smaller page size means uses fewer read operations and creates a "pause" between each request which reduces the impact of a query or scan operation. A larger number of smaller operations can allow other critical requests to succeed without throttling. Reference: Best Practices for Querying and Scanning Data.

QUESTION 4

What does the error "ProvisionedThroughputExceededException" mean in DynamoDB?

    Your EC2 instance has run out of CPU or memory
    
    
    The DynamoDB table is unavailable.
    
    
    The DynamoDB table has exceeded the allocated space.
    
    
    * You exceeded your maximum allowed provisioned throughput for a table or for one or more global secondary indexes.

Good work!

    This error means that you have exceeded your maximum allowed provisioned throughput for a table or for one or more global secondary indexes.

QUESTION 5

DynamoDB is a No-SQL database provided by AWS.

    False
    
    
    * True

Good work!

QUESTION 6

Your application is storing customer order data in a DynamoDB table. You need to run a query to find all the orders
placed by a specific customer in the last month, which attributes would you use in your query?

    The Partition Key of OrderDate and a Sort Key of CustomerID
    
    
    The Partition Key of OrderDate and Sort Key of CustomerName
    
    
    A composite Primary Key made up of the CustomerName and OrderDate

    * The Partition Key of CustomerID and a Sort Key of OrderDate

Good work!

    CustomerName is unlikely to be a unique value in the database, CustomerID is a better choice as will be a unique value. To identify all the orders placed in the last month by a customer, use OrderDate as the Sort Key. The Partition Key of CustomerID would also be more unique than CustomerName.

QUESTION 7

You have an application which reads 80 items of data every second. Each item consists of 3KB. Your application uses
eventually consistent reads. What should you set the RCU read throughput to?

    80 RCU
    
    
    60 RCU
    
    
    20 RCU
    
    
    * 40 RCU

Good work!

    Each Read Capacity Unit represents 2 x Eventually consistent 4KB reads per second. 3KB / 4KB = 0.75 and round up to 1. Multiply that by 80 to give you the figure for Strongly consistent reads. Divide that by 2 to get Eventually consistent reads. Therefore the answer is 40 RCU.

QUESTION 8

A user would like to use the AWS CLI to get the attributes for an item with a specific primary key stored in a DynamoDB
table. In order to do this, they will need IAM permissions for which of the following?

    UpdateItem
    
    
    ListTables
    
    
    * GetItem
    
    
    DescribeTable

Good work!

    GetItem returns a set of attributes for an item with the given primary key.

QUESTION 9

What is the difference between a Global Secondary Index and a Local Secondary Index

Choose 2

    You can create a Local Secondary Index at any time but you can only create a Global Secondary Index at table creation time
    
    
    You can delete a Local Secondary Index at any time
    
    
    * You can delete a Global Secondary Index at any time
    
    
    * You can create a Global Secondary Index at any time but you can only create a Local Secondary Index at table creation time

Good work!

    Only Global secondary Indexes can be created or deleted at anytime. Local Secondary Indexes must be created when you first create the table and they cannot be modified or deleted.

QUESTION 10

By default, a DynamoDB query operation is used for which of the following?

    Find items in a table based on the sort key attribute
    
    
    Return the entire contents of a table
    
    
    * Find items in a table based on the partition key attribute
    
    
    Return the entire contents of a table filtered on the partition key attribute

Good work!

    A query finds items based on the partition key, whereas a scan returns the entire contents of a table. Query.

QUESTION 11

Your low latency web application needs to store its session state in a scalable way so that it can be accessed quickly.
Which service do you recommend?

    In memory on your EC2 instance
    
    
    * DynamoDB
    
    
    RDS
    
    
    Elastic File Store

Good work!

    Using DynamoDB for session storage alleviates issues that occur with session handling in a distributed web application by moving sessions off of the local file system and into a shared location. Amazon DynamoDB provides an effective solution for sharing session state across web servers without incurring drawbacks. Reference: Managing ASP.NET Session State with Amazon DynamoDB.

QUESTION 12

You have an application that needs to read 25 items per second and each item is 13KB in size. Your application uses
eventually consistent reads. What should you set the read throughput to?

    100 RCU
    
    
    25 RCU
    
    
    10 RCU
    
    
    * 50 RCU

Good work!

    Each Read Capacity unit represents 1 x 4KB Strongly Consistent Read. 13KB / 4KB = 3.25 rounded up to 4 multiply by 25 = 100 which gives you the figure for Strongly consistent reads. Divide that by 2 for Eventually consistent. So the answer is 50 RCU.

QUESTION 13

Which of the following approaches is used in AWS to improve flow control by retrying failed requests using progressively
longer waits between retries?

    * xExponential Backoff
    
    
    Exponential Retry
    
    
    Linear Backoff
    
    
    Backoff With Jitter

Good work!

    Each AWS SDK implements an exponential backoff algorithm for better flow control. The idea behind exponential backoff is to use progressively longer waits between retries for consecutive error responses.

QUESTION 14

You are running a query on your Customers table in DynamoDB, however you only want the query to return CustomerID and
EmailAddress for each item in the table, how can you refine the query so that it only includes the required attributes?

    Create a Global Secondary Index which only includes the attributes you need and run the query on the Global Secondary Index
    
    
    Run a query based on the Primary Key and filter the results using a Sort Key of EmailAddress
    
    
    * Use the ProjectionExpression parameter
    
    
    Use a scan operation instead

Good work!

    When using Query, or Scan, DynamoDB returns all of the item attributes by default. To get just some, rather than all of the attributes, use a Projection Expression.

QUESTION 15

Using the AWS Console, you are trying to scale DynamoDB past its pre-configured maximums. Which service limits can you
increase by raising a ticket to AWS support?

Choose 2

    Item Sizes
    
    
    * Global Secondary Indexes per table
    
    
    Local Secondary Indexes
    
    
    * Provisioned throughput limits

Sorry!

    The maximum item size in DynamoDB is 400 KB, which includes both attribute name binary length (UTF-8 length) and attribute value lengths (again binary length). The attribute name counts towards the size limit. Reference: Service, Account, and Table Quotas in Amazon DynamoDB (https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/ServiceQuotas.html)

Correct Answer

    There is an initial quota of 20 global secondary indexes per table. To request a service quota increase, see https://aws.amazon.com/support. Reference: Service, Account, and Table Quotas in Amazon DynamoDB
    
    AWS places some default quotas on the throughput you can provision. These are the quotas unless you request a higher amount. To request a service quota increase, see https://aws.amazon.com/support. Reference: Service, Account, and Table Quotas in Amazon DynamoDB

QUESTION 16

Your application is storing customer order data in DynamoDB. Which of the following pairs of attributes would make the
best composite key to allow you to query DynamoDB efficiently to find a customer order that was placed on a specific
day?

    CustomerID + ProductCategory
    
    
    * CustomerID + OrderDate
    
    
    CustomerID + ProductID
    
    
    CustomerID + Size

Good work!

    To find an order placed on a specific date, use CustomerID and OrderDate as the composite key.

QUESTION 17

Which of the following attributes wouldn't make a good partition key?

    OrderID
    
    
    * InvoiceDate
    
    
    EmailID
    
    
    CustomerID

Good work!

    High-cardinality attributes are recommended for DynamoDB partition keys. These are attributes that have distinct values for each item, like e-mailid, employee_no, customerid, sessionid, orderid, and so on. InvoiceDate provides low-cardinality since many values are repeated for such attribute. Reference: Choosing the Right DynamoDB Partition Key.

QUESTION 18

Your DynamoDB table is throwing a ProvisionedThroughputExceeded error, what could be the problem?

    You are experiencing network contention
    
    
    You are running out of disk space
    
    
    * Your application's request rate is too high
    
    
    Your instance is too small

Good work!

    ProvisionedThroughputExceededException means that your application is sending more requests to the DynamoDB table than the provisioned read / write capacity can handle.

QUESTION 19

Which of the following DynamoDB API calls is used to add a new item into a DynamoDB table?

    UpdateTable
    
    
    UpdateItem
    
    
    GetItem
    
    
    * PutItem

Good work!

    PutItem adds a new item into a table or replaces an old item with a new one.

QUESTION 20

Which of the following services provides in-memory write-through cache optimized for DynamoDB?

    CloudFront
    
    
    Elasticache
    
    
    * DAX
    
    
    Read-replica

Good work!

    DAX or DynamoDB Accelerator is highly available, in-memory cache which is optimized for DynamoDB. DAX currently only offers write-through cache. ElastiCache is supported for use with DynamoDB, however it is not specifically optimized for use with DynamoDB. CloudFront is a Content Delivery Network which caches content like files, web pages, videos etc, but cannot be used to cache Database data. Read-Replicas are used to scale read operations for RDS instances.

QUESTION 21

You have a motion sensor which writes 600 items of data every minute. Each item consists of 5KB. What should you set the
write throughput to?

    * 50

    10

    20

    40

Good work!

    One write request unit represents one write for an item up to 1 KB in size. If you write 600 items every minute, it means 10 items are written per second ( 600 / 60 ). The total number of write capacity units required depends on the item size. If your item size is 5 KB, just multiply 10 items by 5 KB, so you require 50 write capacity units to sustain one write request. Read/Write Capacity Mode.

QUESTION 22

Which feature can you use to capture a time-ordered sequence of all the activity which occurs on your DynamoDB table -
e.g. insert, update, delete?

    Kinesis Data Streams
    
    
    * DynamoDB Streams
    
    
    Amazon CloudWatch
    
    
    AWS CloudTrail

Good work!

    DynamoDB Streams captures a time-ordered sequence of item-level modifications in any DynamoDB table and stores this information in a log for up to 24 hours. Applications can access this log and view the data items as they appeared before and after they were modified, in near-real time. Change Data Capture for DynamoDB Streams.

QUESTION 23

In DynamoDB, a scan operation is used to:

    Find items in a table based on the Sort Key attribute
    
    
    Find items in a table based on the Primary Key values
    
    
    Return the entire contents of a table filtered on the Primary Key attribute
    
    
    * Return all data attributes for every item in the table or index

Sorry!

    By default, a Scan operation returns all of the data attributes for every item in the table or index, but not filtered on the primary key attributes. If you need to further refine the Scan results, you can optionally provide a filter expression.

Correct Answer

    A Scan operation in Amazon DynamoDB reads every item in a table or a secondary index. By default, a Scan operation returns all of the data attributes for every item in the table or index. You can use the ProjectionExpression parameter so that Scan only returns some of the attributes, rather than all of them. Working with Scans in DynamoDB.

QUESTION 24

Which of the following attributes would make a good Partition Key?

    WarehouseLocation
    
    
    * ProductID
    
    
    ProductType
    
    
    Size

Good work!

    It is good practice to use high-cardinality attributes for Partition Keys. in other words, attributes with values that are very uncommon or unique. e.g. ID number, email address, phone number, Social Security Number etc.

QUESTION 25

In terms of performance, a scan is more efficient than a query.

    True
    
    
    * False

Good work!

    In most cases a query is preferable to a scan operation. A scan is generally less efficient & more expensive.






