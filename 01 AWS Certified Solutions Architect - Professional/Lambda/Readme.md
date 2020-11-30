# Lambda

## Acronym
* ECS - Elastic Container Service

## Lambda Integrations Main ones
* API Gateway
* Kinesis
* DynamodB
* S3
* IoT
* CloudWatch Events
* CloudWatch Logs
* SNS
* Cognito 
* SQS

[<img src="https://i.imgur.com/04KEiJf.png">](https://i.imgur.com/04KEiJf.png)

---

## Example
### Serverless Thumbnail creation
[<img src="https://i.imgur.com/IQo2zxA.png">](https://i.imgur.com/IQo2zxA.png)

### Serverless CRON Job
[<img src="https://i.imgur.com/PUqvCYU.png">](https://i.imgur.com/PUqvCYU.png)

---

## Language Support (runtimes)
* Supported:
  * Node.js (JavaScript)
  * Python
  * Ruby
  * Java (Java 8 compatible
  * Golang
  * C# (.NET Core & PowerShell)
* Ability to write/use a custom runtime (community supported):
  * Ex: C++, Rust, etc...
* If Docker, you should use ECS, Fargate or Batch, not Lambda
  
---

## Limits 
* RAM:
  * 128MB to 3Go
* CPU:
  * is linked to RAM (can't be set manually)
  * 2 vCPU are allocated after 1.5Go of RAM
* Timeout: up to 15 min (900s)
* **/tmp** storage: **512MB** (can't process BIG files)
* Deployme
