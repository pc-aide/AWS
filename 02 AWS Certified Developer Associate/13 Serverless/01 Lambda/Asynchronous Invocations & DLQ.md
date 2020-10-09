# Asynchronous Invocations & DLQ

## Doc

## Acronym
* DLQ - Dead Letter Queue
* SNS - Simple Notification Service
* IAM - Identity & Access Managment
* IoT - Internet of Things

## Asynchronous Invocations
* S3, SNS, CloudWatch Events...
* The events are placed in an **Event Queue**
* Lambda attempts to retry on errors:
    * 3 tries totral
    * 1 min wait after 1<sup>st</sup>, then 2 min wait
* Make sure the processing is **idempotent** (in case of retries)
* If the function is retried, you will see **duplicate logs entries in CloudWatch Logs**
* Can define a DLQ - **SNS or SQS** - for failed processing (need correct IAM permissions)
* Asynchronous invocations allow you to speed up the processingif you dont' need to wait for the result
    * ex: you need 1k files processed

### Diagram
[<img src="https://i.imgur.com/kte2gTa.png">](https://i.imgur.com/kte2gTa.png)

---

## Asynchronous Invocations - Services
* S3
* SNS
* CloudWatch Events/EventBridge
* CodeCommit (CodeCommit Trigger: new branch, new tag, new push)
* CodePipeline (invoke a Lambda function during the pipeline, Lambda must callback)
* other
* CloudWatch Logs (log processing)
* Simple Email Service
* cloudFormation
* Config
* IoT
* IoT Events
