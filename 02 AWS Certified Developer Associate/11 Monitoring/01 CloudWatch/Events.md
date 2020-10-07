# Events

## Acronym
* SQS - Simple Queue Service
* SNS - Simple Notification Service
* CW - CloudWatch

## Doc

## Intro
* Schedule: Cron jobs
* Event Pattern: Event rules to react to a service doing something
    * Ex: CodePipeline state changes
* Triggers to Lambda functions, SQS/ SNS/ Kinesis Messages
* CW Event  creates a small json document to give information about the change

---

## Demo
* CW\Events

[<img src="https://i.imgur.com/oioMydZ.png">](https://i.imgur.com/oioMydZ.png)

* Create event
    * Event pattern: CodePipeline
    * Event type: CodePipeline Pipeline Execution State Change
    * Specific state(s): Failed
    * Targets: SNS
    * Topic: ...
    
[<img src="https://i.imgur.com/XGkXYnF.png">](https://i.imgur.com/XGkXYnF.png)
[<img src="https://i.imgur.com/BkxCiMd.png">](https://i.imgur.com/BkxCiMd.png)
[<img src="https://i.imgur.com/CnCvBMt.png">](https://i.imgur.com/CnCvBMt.png)

* Name: CodePipelineFailure

[<img src="https://i.imgur.com/6gzbaoq.png">](https://i.imgur.com/6gzbaoq.png)
[<img src="https://i.imgur.com/twSYQZO.png">](https://i.imgur.com/twSYQZO.png)
