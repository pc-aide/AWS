# CloudWatch

## Acronym
* awscli - AWS Command Line Interface
* SNS - Simple Notification Service
* EC2 - Elastic Compute Cloud
* IAM - Identity & Access Management
* API - Application Programming Interface
* EBS - Elastic Block Store
* S3 - Simple Storage Service
* RDS - Relational database service

## Doc
* [Amazon CloudWatch Documentation](https://docs.aws.amazon.com/cloudwatch/)

## Icon
[<img src="https://i.imgur.com/ubByLIQ.png">](https://i.imgur.com/ubByLIQ.png)

## What is Amazon CloudWatch?
* Monitor Resources & Applications

## AWS Console
[<img src="https://i.imgur.com/BMDgDyd.png">](https://i.imgur.com/BMDgDyd.png)

## Features
[<img src="https://i.imgur.com/1vZKemZ.png">](https://i.imgur.com/1vZKemZ.png)

## Architecture
[<img src="https://i.imgur.com/bVdy0va.png">](https://i.imgur.com/bVdy0va.png)

## Use Case
* Respond to state changes in your AWS resources
* Automatically invoke an AWS Lambda funtion to update DNS entries
  when an event notifies that Amazon EC2 instance enters the Running
  state.
* Direct specific API records fron CloudTrail to a Kinesis stream for
  detailed analysis of potential security or availability risks.
* Take a snapshot of an Amazon EBS volume on a schedule.
* Log S3 Object Level Operations Using CloudWatch Events

## Components
* Metrics
* Alarms
* Events
* Logs
* Dashboards

### Metrics
* Data about the performance of the systems
* Represents in a time-ordered set of data points that are published
  to CloudWatch
* By default, several services provide free metrics for resources.
  * Such as Amazon EC2, Amazon EBS volumes, & Amazon RDS DB instances.
* Publish your own application metrics
* Load all the metrics in your account for search, graphing, & alarms

### Alarms
* Watches a single metric
* Performs one or more actions
  * Based on the value of the metric relative to a threshold over a
    number of time periods
* The action can be :
  * An Amazon EC2 action
  * An Auto Scaling action
  * A notification sent to an Amazon SNS topic
* Invokes actions for sustained state changes only

#### Examples
* Amazon EC2 -> if CPU utilisation is > 60% for 5 minutes...
* Amazon RDS -> if number of simultaneous connection is > 10 for one minute...
* Elastic Load Balancing -> if number of healthy hosts is < 5 for 10 minutes...

## Metrics, Alarms & Actions
[<img src="https://i.imgur.com/eArSE7v.png">](https://i.imgur.com/eArSE7v.png)

### Events
* Near real-time stream of system events that describe changes in AWS resources
* Use simple rules to match events & route them to one or more target functions
  or streams
* Aware of operational changes as they occur
* Respond to these operational changes & takes corrective action as necessary
* Schedule automated actions that self-trigger at certain times using Cron
  or rate expressions
  
  #### Events : Example
  * How to Detect & Automatically Revoke Unintended IAM Access with Amazon
    CloudWatch Events
    
[<img src="https://i.imgur.com/LAFVaUf.png">](https://i.imgur.com/LAFVaUf.png)

### Logs
* Monitor & troubleshoot systems & applications using existing log files
  * Monitor logs for specific phrases, values, or patterns
* Retrieve the associated log data from CloudWatch Logs
* Includes an installable agent for Ubuntu, Amazon Linux, & Windows at no additional charges

#### Logs Features
* Monitor Logs from Amazon EC2 Instances in Real-time
* Monitor AWS CloudTrail Logged Events
* Archive Log Data 

#### Store & Monitor Application Log Files
* Your mettrics can be stored durably in CloudWatch as CloudWatch logs
  * Admins & other parties can review CloudWatch logs directly in the
    AWS Management Console
  * Logs can be stored in Amazon S3, to be accessed by other services
    or another user
  * Logs can be streamed in real time to data-processing solutions
    like Amazon Kinesis Streams or AWS Lambda
    
[<img src="https://i.imgur.com/AKzip2j.png">](https://i.imgur.com/AKzip2j.png)

## awscli
### CloudWatch Agent 
#### Windows
