# Logs

## Acronym
* EB - Elastic Beanstalk
* ECS - Elastic Container Service
* VPC - Virtual Private Cloud
* IAM - Identity & Access Management
* KMS - Key Management Service

## Doc

## Intro
* Applications can send logs to CloudWatch using the SDK
* CloudWatch can collect log from:
    * EB: collection of logs from application
    * ECS: collection from containers
    * Lambda: Collection from functions logs
    * VPC Flow Logs: VPC specific logs
    * API Gateway
    * CloudTrail based on filter
    * CloudWatch log agents: for example on EC2 machines
    * Route 53: Log DNS queries
* CloudWatch Logs can go to:
    * Batch exporter to S3 for archival
    * Steam to ElasticSearch cluster for forther analytics
* CloudWatch Logs can use filter expressions
* Logs storage architecture:
    * Log groups: arbitrary name, usually representing an application
    * Log stream: instances within application/ log files/ containers
* Can define log expiration polcies (never expire, 30 days, etc...)
* Using the AWS CLI we can tail CloudWatch logs
* To send logs to CloudWatch, make sure IAM permissions ar correct
* Security: encryption of logs using KMS at the Group Level

---

## Demo
* CloudWatch\Logs

[<img src="https://i.imgur.com/9Z9ecvm.png">](https://i.imgur.com/9Z9ecvm.png)

* Correction\Edit
    * Metric\ApplicationELB\
    
[<img src="https://i.imgur.com/EPenL9A.png">](https://i.imgur.com/EPenL9A.png)
