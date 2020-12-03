# Step Functions

## URL
* [Sample Project](https://ca-central-1.console.aws.amazon.com/states/home?region=ca-central-1#/sampleProjects)

## Acronym
* ECS - Elastic Container Service
* SNS - Simple Notification Service
* SQS - Simple Queue Service
* DC - Domain Controler

## Intro
* Build serverless visual workflow to orchestrate your Lambda functions
* Represent flow as a JSON **state machine**
* Features: sequence, parallel, conditions, timeouts, error handling...
* Can also integrate with EC2, ECS, on-premise servers, API Gateway
* Maximum **execution time of 1 year**
* Possibility to implement **human approval** feature
* If you chain Lambda function using Step Functions, be mindful of the added latency to pass the calls

---

## Visual workflow 
[<img src="https://i.imgur.com/dWhQ7oJ.png">](https://i.imgur.com/dWhQ7oJ.png)

---

## Sample Projects
* Process high-volume messages from SQS
* Selective checkpointing example
* Train a machine learning model
* Manage a batch job
* Manage an EMR job
* Manage a container task
* Job Poller
* Tune a machine learning model
* Transfer data records
* Task Timer
* etc

### Diagrm
[<img src="https://i.imgur.com/hApvUMv.png">](https://i.imgur.com/hApvUMv.png)

---

## Tasks
* <ins>Lambda Task:</ins>
  * Invoke a Lambda function
* <ins>Activity Tasks:</ins>
  * Activity worker (HTTP), EC2 Instances, mobile device, on-premise DC
  * They poll the Step functions service
* <ins>Service Tasks:</ins>
  * Connect to a supported AWS service
  * Lambda function, ECS Task, Fargate, DynamoDB, Batch job, SNS topic, SQS queue
* <ins>Wait Task:</ins>
  * To wait for a duration or until a timestamp
* **Note**: Step Functions does not integrate natiely with AWS **Mechanical Turk**

---

## Solution Architecture
[<img src="https://i.imgur.com/zcdaUr4.png">](https://i.imgur.com/zcdaUr4.png)
