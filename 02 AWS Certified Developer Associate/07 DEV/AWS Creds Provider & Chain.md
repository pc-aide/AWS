# AWS Creds Provider & Chain

## Acronym
* CLI - Command-Line Interface
* ECS - Elastic Container Service
* IAM - Identity & access management

## Doc

## Intro
* The CLI will look for credentials in this order
    1) **Command line options**: --region, --output, & --profile
    2) **Environment variables**: AWS_ACCESS_KEY_ID, AWS_SECRET_ACCESS_KEY, & AWS_SESSION_TOKEN
    3) **CLI credentials file**: aws configure
        * ~/.aws/credentials on Linux / Mac
        * c:\\Users\\user\\.aws\\credentials on Windows
    4) **CLI configuration file**: aws configure
        * ~/.aws/config on Linux / Mac & c:\\Users\\UserName\\.aws\\config on Windows
    5) **Container credentials**: for ECS tasks
    6) **Instance profile credentials**: for EC2 Instance Profiles
    
---

## AWS SDK Default Credentials Provider Chain
* The Java SDK (example) will look for credentials in this order
    1) **Environment variables**
        * AWS_ACCESS_KEY_ID & AWS_SECRET_ACCESS_KEY
    2) **Java system properties**: aws.accessKeyId & aws.secretkey
    3) **The default credential profiles file**: ex at: ~/.aws/credentials, shared by many SDK
    4) **Amazon ECS container credentials**: for ECS containers
    5) **Instance profile credentials**: used on EC2 instances
    
---

## aWS Credentials Scenario
* An application deployed on an EC2 instance is using encironment variables with credentials from an IAM user to call the Amazon S3 API
* The IAM user has **S3FullAccess** permissions
* The application only uses one S3 bucket, so according to best practices
        * An **IAM Role** & EC2 Instance Profile was crated for the EC2 instance
        * The Role was assigned the minimum permissions to access that one S3 bucket
* The IAM Instance Profile was assigned to the EC2 instance, but it still had access to all S3 buckets. Why?
        * <ins>the credentials chain is still giving priorities to the environment variables</ins>
        
---

## AWS Credentials Best Practices
* Overall, NEVER EVER STORE AWS CREDENTIALS IN YOUR CODE
* Best practice is for credentials to be inherited from the credentials chain
* If using working within AWS, use **IAM Roles**
        * => EC2 Instances Roles for EC2 Instances
        * => ECS Roles for ECS tasks
        * => Lambda Roles for Lambda functions
* If working outside of AWS, use encironment variables / named profiles
