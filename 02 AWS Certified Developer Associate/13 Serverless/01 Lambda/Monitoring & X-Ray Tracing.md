# Monitoring & X-Ray Tracing

## Acronym
* CW - CloudWatch
* IAM - Idenity & Access Managmenet
* SDK - Software Development Kit

## Doc

## Lambda Loggin & Monitoring
* CloudWatch Logs:
    * Lambda execution logs are stored in CW Logs
    * Make sur your Lambda function has an execution role iwht an IAM policy
      that authorizes writes to CW Logs
* CW Metrics
    * Lambda metrics are displayed in CW Metrics
    * Invocations, Durations, Concurrent Executions
    * Error count, Success Rates, Throttles
    * Async Delivery Failures
    * Iterator Agen (Kinesis & DynamoDB Streams)
    
---

## Lambda Tracing with X-Ray
* Enable in Lambda configuration (**Active Tracing**)
* Runs the X-Ray daemon for you
* Use X-Ray SDK in Code
* Ensure Lambda Function has a correct IAM Execution Role
    * The managed policy is called AWSXRayDaemonWriteAccess
* Environment vairables to communicate with X-Ray
    * **_X_AMZN_TRACE_ID**: contains the tracing header
    * **AWS_XRAY_CONTEXT_MISSING**: by default, LOG_ERROR
    * **AWS_XRAY_DAEMON_ADDRESS**: the X-Ray Daemon IP_ADDRESS:PORT
    
---

## Demo
* Demo-Lambda\Monitoring\
* Demo-S3\Monitoring\

[<img src="https://i.imgur.com/kGWCk3F.png">](https://i.imgur.com/kGWCk3F.png)
[<img src="https://i.imgur.com/57qEcDg.png">](https://i.imgur.com/57qEcDg.png)
[<img src="https://i.imgur.com/QfRpVAv.png">](https://i.imgur.com/QfRpVAv.png)

* Active tracing (X-Ray):

[<img src="https://i.imgur.com/PKxk1SW.png">](https://i.imgur.com/PKxk1SW.png)
[<img src="https://i.imgur.com/r6rmtmc.png">](https://i.imgur.com/r6rmtmc.png)
[<img src="https://i.imgur.com/0zaSm48.png">](https://i.imgur.com/0zaSm48.png)

* Lambda\Permissions\Role name:
