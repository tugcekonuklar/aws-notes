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

Which IAM entity can you use to delegate access to trusted entities such as IAM users, applications, or AWS services such as EC2?

    IAM User

    IAM Group
    
    * IAM Role

    IAM Web Identity Federation

Good work!

    You can use IAM roles to delegate access to IAM users managed within your account, to IAM users under a different AWS account, to a web service offered by AWS such as Amazon Elastic Compute Cloud (Amazon EC2), or to an external user authenticated by an external identity provider (IdP) service that is compatible with SAML 2.0 or OpenID Connect, or a custom-built identity broker. IAM Roles.











