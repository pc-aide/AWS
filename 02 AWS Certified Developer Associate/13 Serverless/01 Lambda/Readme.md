# Lambda

## Acronym
* vSRV - Virtual Server
* ECS - Elastic Container Service
* SQS - Simple Queue Service
* SNS - Simple Notification Service

## Doc
* [AWS Lambda Pricing](https://aws.amazon.com/lambda/pricing/)

## Intro
* EC2
    * vSRV in the Cloud
    * Limited by RAM & CPU
    * continuously running
    * Scaling means intervention to add/remove servers
* Lambda
    * Virtual **functions** - **no server to manage**
        * Just need to provision the coe & the functions run
    * Limited by time - **short executions**
        * ex.: up to 15 minutes
    * Run **on-demand**
    * Scaling is automated
        * if your need more Lambda functions, & different currency, then automatically, AWS will provision for you, more Lambda  functions

### Diagram
[<img src="https://i.imgur.com/TLwzoqg.png">](https://i.imgur.com/TLwzoqg.png)

---

## Benefits
* Easy Pricing:
    * Pay per request & compute time
    * Free tier of 1 Millions Lambda request & 400k GBs of compute time 
* Integrated with the whole AWS suite of services
* Integrated with many programming languages
* Easy monitoring through CloudWatch
* Easy to get more resources per functions (up to 3GB of RAM)
* Increasing RAM will also improve CPU & network

---

## Lambda language support
* Node.js  (JavaScript)
* Python
* Java (Java 8 compatible)
* C# (.NET Core)
* Golang
* C# / PowerShell
* Ruby
* Custom Runtime API (community supported, example Rust)
* **Important: Docker** is not for Lambda, it's for ECS/Fargate

---

## Lambda Integrations Main ones
* API Gateway
* Kinesis
* DynamoDB
* S3
* CloudFront
* CloudWatch Events EventBridge
* CloudWatch Logs
* SNS
* SQS
* Cognito

[<img src="https://i.imgur.com/T2XhX9y.png">](https://i.imgur.com/T2XhX9y.png)

---

## Example
* Serverless Thumbnail creation:

[<img src="https://i.imgur.com/qvDwCcN.png">](https://i.imgur.com/qvDwCcN.png)

---

## Another Example
* Serverless CRON Job:

[<img src="https://i.imgur.com/H3Yi9Wi.png">](https://i.imgur.com/H3Yi9Wi.png)

---

## Example: Lambda Pricing
* 
