# 07 DEV

## Acronym
* EC2 - Elastic Compute Cloud
* RDS - Relational database service
* DB - Database
* std - standard
* URL - Uniform Resource Locator
* ASG - Atuo-Scaling Group
* ELB - Elastic Load Balancing
* CLI - Command Line-Interface

## Doc

## Intro
* So far, we've interacts with services manually & they exposed standard information for clients:
    * EC2 exposes a std Linux machine we can use nay way we want
    * RDS exposes a std db we can connect to using a URL
    * **ElastiCache** exposes a **chache URL** we can connect to using a URL
    * ASG/ELB are automated & we don't have to program against them
    * Route 53 was setup manual
* Developing against AWS has two components:
    * How to perform interactions with AWS without using the Online Console?
    * How to interact with AWS Proprietary services? (S3, DynamoDB, etc...)
* Developing & peforming AWS tasks against AWS can be done in several ways
    * Using the AWS CLI on our local computer
    * Using the AWS CLI on our EC2 machines
    * Using the AWS SDK on our local computer
    * Using the AWS SDK on our EC2 machines
    * Using the AWS Instance Metadata Service for EC2
