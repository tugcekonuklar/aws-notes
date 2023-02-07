_# Architecting on AWS

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

# Networking

# Compute

# Storage

# Database Services

# Monitoring and Storing

# Automation

# Containers

# Serverless

# Edge Services

# Backup and Recovery_