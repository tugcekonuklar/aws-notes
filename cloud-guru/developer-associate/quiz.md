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

You are hosting a website in an Amazon S3 bucket. Which feature defines a way for client web applications that are loaded in one domain to interact with resources in a different domain?


    Bucket ACL
    
    
    IAM Role
    
    
    Bucket Policy
    

    * CORS

Good work!
    
    Cross-origin resource sharing (CORS) defines a way for client web applications that are loaded in one domain to interact with resources in a different domain. With CORS support, you can build rich client-side web applications with Amazon S3 and selectively allow cross-origin access to your Amazon S3 resources. Reference: Configuring and using cross-origin resource sharing (CORS).



QUESTION 3

You are hosting a static website in an S3 bucket that uses Javascript to reference assets in another S3 bucket. For some reason, these assets are not displaying when users browse to the site. What could be the problem?


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

Which storage class is suitable for long-term archiving of data that occasionally needs to be accessed within a few hours or minutes?


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

You are using S3 in ap-northeast-1 to host a static website in a bucket called "acloudguru". What would the new URL endpoint be?

    
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

You would like to configure your S3 bucket to only serve content over HTTPS/SSL and explicitly deny all unencrypted HTTP access. In your bucket policy, how should you specify the type of request that should be denied?

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

You would like to configure your S3 bucket to deny put object requests that do not use server-side encryption. Which bucket policy can you use to deny permissions to upload objects, unless the request includes server-side encryption?

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

You would like to migrate your website to AWS and use CloudFront to provide the best performance. Your users will need to complete a form on the website in order to subscribe to a mailing list and comment on blog posts. Which of the following allowed HTTP methods should you configure in your CloudFront distribution settings?


    * GET, HEAD, OPTIONS, PUT, POST, PATCH, DELETE

    GET, HEAD

    GET, HEAD, OPTIONS, POST
    
    GET, HEAD, OPTIONS

Good work!

    This combination of HTTP methods will enable your users to interact with the website and send, modify, insert, and delete data.


