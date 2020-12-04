# CloudWatch

## Acronym
* CW - CloudWatch
* SSE - Side-Server Encryption
* ES - Elastic Search
* EB - Elastic Beanstalk
* KMS - Key Management Service
* SNS - Simple Notification Service
* SSM - System Manager
* SQS - Simple Queue Service
* ECS - Elastic Container Service

## Intro
* CW Metrics
  * Provided by many AWS services
  * EC2 standard: 5min, detailed monitoring: 1min
  * EC2 RAM is not a bult-in metric
    * Maybe use  hte CW Unified Agent
  * Can create custom metrics: standard resolution 1min, high resolution 1sec
* CW Alarms
  * Can trigger actions:
    * EC2 action
      * Reboot
      * Stop
      * Terminate
      * Recover
    * Auto Scaling
    * SNS 
  * Alarms events can be intercepted by CW Events   
* CW Dashboards
  * Display metrics & alarms
  * Can show metrics of multiple regions
  
---

## CW Alarms integrations
[<img src="https://i.imgur.com/aE6fRtW.png">](https://i.imgur.com/aE6fRtW.png)

---

## CW Events
* Intercept events from AWS services
* Example: EC2 Instance Start, CodeBuild Failure, S3, Trusted Advisor
* Can intercept any API call with CloudTrail integration
* <ins>Notable targets:</ins>
  * **Compute**: Lambda, Batch, ECS task
  * **Orchestration**: Step Functions, CodePipeline, CodeBuild
  * **Integration**: SQS, SNS, Kinesis Data Streams, Kinesis Data Firehose
  * **Maintenance**: SSM, EC2 Actions
  
---

## CW Logs - Sources
* SDK, CW Logs Agent, CW Unified Agent
* EB: collection of logs from application
* ECS: collection from containers
* Lambda: collection from function logs
* VPC Flow Logs: VPC specific logs (log streams)
* API Gateway
* CloudTrail based on filter
* CW log agent: for example on EC2 machines
* Route 53: Log DNS queries

---

## CW Logs
* **Log groups**: arbitrary name, usually representing an application
* **Log stream**: instances within application/log files/containers
* Can define log expiration policies (never expire, 30 days, etc...)
* Optional KMS encryption
* CW Logs can send logs to:
  * S3 (exports)
  * Kinesis Data Streams
  * Kinesis Data Firehose
  * Lambda
  * ES
  
---

## CW Logs Metric Filter & Insights
* CW Logs can use filter expressions
  * For example, find a specific IP inside of a log
  * Or count occurences of "ERROR" in your logs
  * Metric filters can be used to trigger alarms
* CW Logs **Insights** can be used to query logs & add queries to CW Dashboard:

[<img src="https://i.imgur.com/3vQnk2i.png">](https://i.imgur.com/3vQnk2i.png)

---

## CW Logs - S3 Export
* if you want to analyze the logs with own tools
* S3 buckets must be encrypted AES-256 (SSE-S3), **not SSE-KMS**
* Log data can take **up to 12 hours** to become available for export
* The API call is **CreateExportTask**
* Not near-real time or real-time... use Logs Subscriptions instead

### Diagram
[<img src="https://i.imgur.com/12PIDYy.png">](https://i.imgur.com/12PIDYy.png)

---

## CW Logs Subscriptions
[<img src="https://i.imgur.com/E0WFl7z.png">](https://i.imgur.com/E0WFl7z.png)

--- 

## CW Logs Aggregation Multi-Account & Multi-Region
[<img src="https://i.imgur.com/gD2pYre.png">](https://i.imgur.com/gD2pYre.png)

---

## CW Logs Agent & Unified Agent
* For vitual servers (EC2 instances, on-premise servers...)
* CW Logs Agent
  * Old version of the agent
  * Can only send to CW Logs
* CW Unified Agent
  * new version of the agent
  * Collect additonal system-level metrics such as RAM, processes, etc...
  * Collect logs to send to cW Logs
  * Centralized configuration using SSM Parameter Store
* Batch Sends
  * batch_count: number of log events to send (default 10k, min 1)
  * batch_duration: duration of batching for log events (default & min is 5000ms
  * batch_size: max size of log events in a batch (default & max is 1MB)
* **Both agents can't send logs to Kinesis**:
  * CW Logs Agent
  * CW Unified Agent
  * we need use the Kinesis agent instead
