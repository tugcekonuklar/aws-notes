# Architecting on AWS

# Outlook

* [Fundamentals](#fundamentals)
* [Account Security](#account-security)
* [Networking](#networking)
* [Compute](#compute)
* [Storage](#storage)
* [Database Services](#database-services)
* [Monitoring and Storing](#monitoring-and-storing)
* [Automation](#automation)
* [Containers](#containers)
* [Serverless](#serverless)
* [Edge Services](#edge-services)
* [Backup and Recovery](#backup-and-recovery)

# Fundamentals

* AWS is the world’s most comprehensive and adopted cloud solution.
    * AWS offers services such as compute, database, and storage.
    * The AWS pay-as-you-go model, and its security practices, have made AWS the preferred cloud solution for businesses
      and public organizations.
* <img src="./img/4.png" alt="alt text" width="500" height="300">
* Product list [here](https://aws.amazon.com/products/)

## AWS infrastructure

* <img src="./img/5.png" alt="alt text" width="500" height="300">
* [AWS data Centers](https://aws.amazon.com/compliance/data-center/data-centers/)
    * <img src="./img/6.png" alt="alt text" width="500" height="300">
* AWS Availability Zones [Global infra](https://aws.amazon.com/about-aws/global-infrastructure/):
    * A group of Data center called Availability Zones (AZ)
    * An Availability Zone is one or more discrete data centers with redundant power, networking, and connectivity in an
      AWS Region.
    * <img src="./img/7.png" alt="alt text" width="500" height="300">
* AWS Region [Region AZ](https://aws.amazon.com/about-aws/global-infrastructure/regions_az/)
    * Each AWS Region consists of multiple isolated and physically separate Availability Zones within a geographic area.
      This achieves the greatest possible fault tolerance and stability. In your account, you determine which Regions
      you need
    * <img src="./img/1.png" alt="alt text" width="500" height="300">
    * Factors impact Region Selection:
        * Governance and legal requirements – Consider any legal requirements based on data governance, sovereignty, or
          privacy laws.
        * Latency – Close proximity to customers means better performance.
        * Service availability – Not all AWS services are available in all Regions.
        * Cost – Different Regions have different costs.
* AWS Local Zones [Local zones](https://aws.amazon.com/about-aws/global-infrastructure/localzones/) :
    * AWS Local Zones can use for highly demanding applications that require single-digit millisecond latency to end
      users, For example:
        * Media and entertainment content creation – Includes live production, video editing, and graphics-intensive
          virtual workstations for artists in geographic proximity
        * Real-time multiplayer gaming – Includes real-time multiplayer game sessions, to maintain a reliable gameplay
          experience
        * Machine learning hosting and training – For high-performance, low latency inferencing • Augmented reality (AR)
          and virtual reality (VR) – Includes immersive entertainment, data driven insights, and engaging virtual
          training experiences
    * <img src="./img/2.png" alt="alt text" width="500" height="300">  
* Edge Location:
    * An edge location is the nearest point to a requester of an AWS service. Edge locations are located in major cities
      around the world. They receive requests and cache copies of your content for faster delivery.
    * You employ a worldwide network of edge sites that enable AWS services to provide content to users with lower
      latency.
        * Through a global point of presence (PoP) network made up of edge locations and regional edge cache servers,
          CloudFront distributes customer content.
        * When you have content that is not accessed frequently enough to stay in an edge location, regional edge
          caches—used by default with CloudFront—are employed.
        * This content is absorbed by local edge caches, eliminating the need to retrieve it from the origin server.
        * [AWS Cloud Front Key Features](https://aws.amazon.com/cloudfront/features/?whats-new-cloudfront.sort-by=item.additionalFields.postDateTime&whats-new-cloudfront.sort-order=desc)
        * For example:
            * edge locations is to serve content closer to your customers. An example of a video file
              stored in Amazon Simple Storage Service (Amazon S3) in South America. The file is cached to an edge
              location near the customer to serve the video file faster to a customer in A
    * <img src="./img/3.png" alt="alt text" width="500" height="300">  
* When to use AWS Local Zones?
    * You should use AWS Local Zones to deploy AWS compute, storage, database, and other services closer to your end
      users for low-latency requirements. With AWS Local Zones, you can use the same AWS infrastructure, services, APIs,
      and tool sets that you are familiar with in the cloud
* When to use AWS Edge Locations?
    * You should use edge locations for caching the data (content) to provide fast delivery of content for users. Using
      edge locations allows for a better user experience, providing faster delivery to users at any location.

## AWS Well-Architecture Framework

* [AWS Well Architecture tools](https://aws.amazon.com/architecture/well-architected/?wa-lens-whitepapers.sort-by=item.additionalFields.sortDate&wa-lens-whitepapers.sort-order=desc&wa-guidance-whitepapers.sort-by=item.additionalFields.sortDate&wa-guidance-whitepapers.sort-order=desc)
* [AWS Well Architect Labs](https://www.wellarchitectedlabs.com/)
* [AWS Well-Architected Tool – Review Workloads Against Best Practices](https://aws.amazon.com/blogs/aws/new-aws-well-architected-tool-review-workloads-against-best-practices/)
    * The AWS WA Tool is a self-service tool you can use to review the state of your existing workloads and compare them
      to the latest AWS architectural best practices. It is designed to help architects and their managers review AWS
      workloads without the need for an AWS SA. This service is based on the AWS Well-Architected Framework
* [Successful solutions architects do these five things](https://aws.amazon.com/blogs/training-and-certification/successful-solutions-architects-do-these-five-things/)
* <img src="./img/8.png" alt="alt text" width="500" height="300">  
* The AWS Well-Architected Framework helps cloud architects build secure, high-performing, resilient, and efficient
  application infrastructures. It is a consistent approach for customers and partners to evaluate architectures and
  implement designs that can scale over time
* <img src="./img/9.png" alt="alt text" width="500" height="300">
* The architectural reviews focus on the following:
    * Security – Use AWS security best practices to build policies and processes to protect data and assets. Allow
      auditing
      and traceability. Monitor, alert, and audit actions and changes to your environment in real time.
    * Cost optimization – Achieve cost efficiency while considering fluctuating resource needs. • Reliability – Meet
      well-defined operational thresholds for applications. This includes support to recover from failures, handling
      increased
      demand, and mitigating disruption.
    * Performance efficiency – Deliver efficient performance for a set of resources like instances, storage, databases,
      space, and time.
    * Operational excellence – Run and monitor systems that deliver business value. Continually improve supporting
      processes
      and procedures.
    * Sustainability – Minimize and understand your environmental impact when running cloud workloads.

# Account Security

* When you create first an AWS account you create root account.
* AWS strongly recommends that you not use root account credentials for day-to-day interactions with AWS. Create users
  for everyday tassk
* Create your additional users and assign permissions to these users following the principle of least privilege.
    * Grant users only the level of access they require and nothing
      more [AWS Identity and Access Management User Guide](https://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html#grant-least-privilege)
* Use IAM to control who is authenticated (signed in) and authorized (has permissions) to use resources
* [policies and Permissions](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies.html)
* Principal:
    * A principal is an entity that can request an action or operation on an AWS resource. IAM users and IAM roles are
      the most common principals you work with,
    * A principal can also be an AWS service , like Amazon Elastic Compute Cloud (ec2)
* [Federated users](https://aws.amazon.com/identity/federation/) are external users and AWS is not manage those users
    * <img src="./img/10.png" alt="alt text" width="500" height="300">

* **IAM **:
    * By default, a new IAM user has no permissions to do anything. The user is not authorized to perform any AWS
      operations or access any AWS resources.
    * An advantage of having individual IAM users is that you can assign permissions individually to each user
    * <img src="./img/11.png" alt="alt text" width="500" height="300">
    * [AWS Identity and Access Management User Guide](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_users.html)
* [To setup AWS CLI in your client](https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-quickstart.html)
* **IAM USer Group:**
    * An IAM user group is a collection of IAM users. With user groups, you can specify permissions for multiple users,
      which makes it easier to manage the permissions.
    * [AWS User Group](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_groups.html)
* **IAM Roles:**
    * IAM roles deliver temporary AWS credentials.
    * They’re easy to manage because multiple employees and applications can use the same role.
    * There are no charges for using roles
    * Use roles to delegate access to users, applications, or services that don't normally have access to your AWS
      resources.
    * <img src="./img/12.png" alt="alt text" width="500" height="300">
* **Assuming a Role:**
    * <img src="./img/13.png" alt="alt text" width="500" height="300">
    * You assume a role using a trusted entity, such as an IAM user, an AWS service, or a federated user
    * AWS services can use the same API call to assume roles in your AWS accounts.
    * Federated users use either the AssumeRoleWithSAML or AssumeRoleWithWebIdentity API calls
    * The API call is made to AWS Security Token Service (AWS STS).
    * AWS STS is a web service that provides temporary, limited-privilege credentials for IAM or federated
      users.
        * It returns a set of temporary security credentials consisting of an access key ID, a secret access key, and
          a security token. These credentials are then used to access AWS resources.
    * The AssumeRole API is typically used for cross-account access or federation.
        * [AWS Security Token Service API Reference ](https://docs.aws.amazon.com/STS/latest/APIReference/welcome.html)
* Security Policy types
    * Policy types
        * **Identity-based policies** – Attach managed and inline policies to IAM identities. This includes users,
          groups to
          which users belong, and roles.
            * Identity-based policies are JSON permissions policy documents that control:
                * What actions an IAM identity (users, groups of users, and roles) can perform
                * On which resources
                * Under what condition
            * Identity-based policies can be categorized by the following types:
                * **Managed policies –** Standalone identity-based policies that you can attach to multiple users,
                  groups, and roles in your AWS account. There are two types of managed policies: o AWS managed policies
                    * **Managed policies** that are created and managed by AWS. They are built to provide specific
                      service access or permissions for job functions.
                    * **Customer managed policies -** Managed policies that you create and manage in your AWS account.
                      Customer managed policies provide more precise control over your policies than AWS managed
                      policies.
                * **Inline policies –** Policies that you add directly to a single user, group, or role. Inline policies
                  maintain a strict one-to-one relationship between a policy
                    * An inline policy is one that you create and embed directly to an IAM group, user, or role. Inline
                      policies can't be reused on other identities or managed outside of the identity where they exist.
                    * [Use customer managed policies instead of inline policies](https://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html#best-practice-managed-vs-inline)
            * **Resource-based policies** – Attach inline policies to resources. The most common examples of
              resource-based
              policies are Amazon S3 bucket policies and IAM role trust policies.
                * Resource-based policies are JSON policy documents that you attach to a resource such as an Amazon S3
                  bucket.
                * These policies grant the principal permission to perform specific actions on that resource and define
                  under what conditions this applies.
                * Resource-based policies are inline policies. There are no managed resource-based policies.
        * **AWS Organizations service control policies (SCPs)** – Use Organizations SCPs to define the maximum
          permissions for account members of an organization or organizational unit (OU).
        * **IAM permissions boundaries** - AWS supports permissions boundaries for IAM entities (users or roles). Use
          IAM permissions boundaries to set the maximum permissions that an IAM entity can receive.

* Identity Based Policy example
    * <img src="./img/16.png" alt="alt text" width="500" height="300">
    * A JSON identity-based policy document includes these elements:
        * Version – The Version policy element specifies the language syntax rules that are to be used to process a
          policy. To use all of the available policy features, include the value “2012-10-17” for the version in your
          policies.
        * Effect – Use Allow or Deny to indicate whether the policy allows or denies access.
        * Action (or NotAction) – Include a list of actions that the policy allows or denies.
        * Resource (or NotResource) – You must specify a list of resources to which the actions apply.
        * Condition (or NotCondition) – Specify the circumstances under which the policy grants permission.
* By default, all requests are implicitly denied with the exception of the AWS account root user, which has full access.
  This is called an implicit deny.
    * An explicit allow in an identity-based or resource-based policy overrides this default.
    * An explicit deny in any policy overrides any allows

* Resource-based policy example:
    * <img src="./img/17.png" alt="alt text" width="500" height="300">
    * Resource-based policies are attached to a single resource, like an S3 bucket or AWS Lambda function.
    * With resource-based policies, you choose who has access to the resource and what actions they can perform on it.
    * you must list the **principal** account, user, role, or federated user to which you want to allow or deny access.
      If you are creating an IAM permissions policy to attach to a user or role, you cannot include this element. The
      principal is implied as that user or role
    * The **resource** element is optional. If you do not include this element, the resource to which the action applies
      is the resource to which the policy is attached.
* Defense in depth:
    * Defense in depth is a strategy focused on creating multiple layers of security
    * <img src="./img/18.png" alt="alt text" width="500" height="300">
    * In this example different users try to access a document in your S3 bucket. Each user needs an
      identity-based policy assigned to either their user or a role they assume to access AWS. They then navigate
      through layers of resource-based policies—first a VPC endpoint policy, then a bucket policy for the S3 bucket.
      Your users are able to access the documents they need for their task. You will learn more about VPC endpoints and
      S3 buckets later in this course
    * [policy evaluation logic](https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_policies_evaluation-logic.html)

* IAM Permissions boundaries
    * AWS supports permissions boundaries for IAM entities—users or roles.
    * A permissions boundary is an advanced feature for using a managed policy to set the maximum permissions that an
      identity-based policy can grant to an IAM entity.
    * Permissions boundaries act as a filter.
    * An entity's permissions boundary allows it to perform only the actions that are allowed by both its identity-based
      policies and its permissions boundaries.
    * [Permissions boundaries for IAM entities](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_boundaries.html)

## Managing multiple aws accounts

* AWS Organization:
* <img src="./img/19.png" alt="alt text" width="500" height="300">
* AWS Organizations provides these key features:
    * Centralized management of all your AWS accounts
    * Consolidated billing for all member accounts
    * Hierarchical grouping of your accounts to meet your budgetary, security, or compliance needs
    * Policies to centralize control over the AWS services and API actions that each account can access
    * Policies to standardize tags across the resources in your organization's accounts
    * Policies to control how AWS artificial intelligence (AI) and machine learning (ML) services can collect and store
      data
    * Policies that configure automatic backups for the resources in your organization's accounts
    * Integration and support for IAM
    * Integration with other AWS services
    * Global access
    * Data replication that is eventually consistent
    * No cost for use
* [Inheritance for service control policies](https://docs.aws.amazon.com/organizations/latest/userguide/orgs_manage_policies_inheritance_auth.html)

* Service Control Policy (SCPs):
    * An SCP is a type of organization policy that you can use to manage permissions in your organization. SCPs:
        * Offer central control over the maximum available permissions for all accounts in your organization
        * Help your accounts stay within your organization’s access control guidelines
        * Are available only in an organization that has all features turned on
    * AWS Organizations is a service for grouping and centrally managing the AWS accounts that your business owns. If
      you enable all features in an organization, then you can apply service control policies (SCPs) to any or all of
      your accounts.
    * Attaching an SCP to an Organizations entity (root, OU, or account) defines a guardrail. SCPs set limits upon the
      actions that the IAM users and roles in the affected accounts can perform.
    * To grant permissions, you need to attach identity-based or resource-based policies to IAM users, or to the
      resources in your organization's accounts.
    * When an IAM user or role belongs to an account that is a member of an organization, the SCPs limit the user's or
      role's effective permissions.
    * <img src="./img/20.png" alt="alt text" width="500" height="300">
    * In the example, an SCP allows all EC2 and S3 actions. A collection of IAM identity-based permissions allow all EC2
      and IAM actions. The effective allowed permissions for the IAM identity are all EC2 actions. It excludes both S3
      and IAM actions because they are not explicitly allowed in both policy types.

# Networking

* **CIDR**:
    * CIDR notation defines an IP address range for a network or a subnet. This range is referred to as a CIDR block.
    * When building your network in AWS using VPC components, you specify CIDR blocks for your VPC and subnets. You must
      allocate enough IP addresses to support the resources on your network. Your VPC can have up to five CIDR blocks,
      and their address ranges cannot overlap.
    * Amazon VPC supports Ipv4 and IPv6 it has different CIDR blocks, IPV4 is default defined for all VPCs, you can not
      change this behaviour.
    * <img src="./img/21.png" alt="alt text" width="500" height="300">
* **VPC Fundamentals:**
    * <img src="./img/22.png" alt="alt text" width="500" height="300">
    * With Amazon VPC, you can launch AWS resources into a virtual network that you have defined. VPCs deploy into one
      of the AWS Regions and can host resources from any Availability Zone within its Region.
    * Amazon VPC is designed to provide greater control over the isolation of your environments and their resources.
    * With Amazon VPC, you can:
        * Select your own IP address range
        * Create subnets
        * Configure route tables and network gateway
    * [What is VPC?](https://docs.aws.amazon.com/vpc/latest/userguide/what-is-amazon-vpc.html)
    * <img src="./img/23.png" alt="alt text" width="500" height="300">
* **Subnet**:
    * <img src="./img/24.png" alt="alt text" width="500" height="300">
    * A subnet is a range of IP addresses in your VPC.
    * Use a public subnet for resources that must be connected to the internet and a private subnet for resources that
      won't be connected to the internet. A subnet resides within one Availability Zone.
    * The first four IP addresses and the last IP address in each subnet CIDR block are not available and cannot be
      assigned to an instance.
        * For example, in a subnet with CIDR block 10.0.0.0/24, the following five IP addresses are reserved:
            * 10.0.0.0: Network address.
            * 10.0.0.1: Reserved by AWS for the VPC router.
            * 10.0.0.2: Reserved by AWS. The IP address of the DNS server is always the base of the VPC network range
              plus 2.
            * 10.0.0.3: Reserved by AWS for future use.
            * 10.0.0.255: Network broadcast address. We do not support broadcast in a VPC; therefore, we reserve this
              address.

* Public Subnet:
    * Your public subnet configuration acts as a two-way door—allowing traffic to flow in either direction, invited or
      not invited.
    * Since there is no automatic outbound routing, you must configure a subnet to be public.
    * A public subnet requires the following:
        * Internet gateway: The internet gateway allows communication between resources in your VPC and the internet.
        * Route table: A route table contains a set of rules (routes) that are used to determine where network traffic
          is directed. It can direct traffic to the internet gateway.
        * Public IP addresses: These are addresses that are accessible from the internet. Public IP addresses obscure
          the private IP addresses, which are only reachable within the network.

* Internet gateway:
    * internet gateway is a horizontally scaled, redundant, and highly available VPC component that permits
      communication between instances in your VPC and the internet. It imposes no availability risks or bandwidth
      constraints on your network traffic
    * An internet gateway serves two purposes:
        * It provides a target in your route table for internet-routable traffic.
        * It protects IP addresses on your network by performing network address translation (NAT).
    * **Provides a target in your route table for internet-routable traffic**
        * A subnet does not allow outbound traffic by default. Your VPC uses route tables to determine where to route
          traffic. To allow your VPC to route internet traffic, you create an outbound route in your route table with an
          internet gateway as a target, or destination
    * **Protects IP addresses on your network by performing network address translation (NAT)**
    * Resources on your network that connect to the internet should use two kinds of IP addresses:
        * Private IP: Use private IPs for communication within your private network. These addresses are not reachable
          over the internet.
        * Public IP: Use public IP addresses for communication between resources in your VPC and the internet. A public
          IP address is reachable over the internet.
    * [Connect to the internet using an internet gateway](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_Internet_Gateway.html)

# Compute

# Storage

# Database Services

# Monitoring and Storing

# Automation

# Containers

# Serverless

# Edge Services

# Backup and Recovery_