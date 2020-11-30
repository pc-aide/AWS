# Lambda

## Acronym
* ECS - Elastic Container Service
* NAT - Network Address Translation
* SNS - Simple Notification Service
* IGW - Internet Gateway
* RDS - Relational Database Service
* IAM - Identity & Access Management
* VPC - Virtual Private Cloud
* SQS - Simple Queue Service
* ELB - Elastic Load Balancer
* ALB - Application Load Balancer

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
* Deployment package limit: **250MB** including layers
* Concurrency execution:**1k** - soft limit that can be increased

---

## Latencies Considerations (approximates)
* Lambda Latency:
  * Cold Lambda Invocation: ~100ms
  * Warm Lambda Invocation:~ms
  * New feature of "**provisioned concurrency**" (Dec 2019) to reduce # of cold starts
* API Gateway invocation: 100ms
* CloudFront invocation: 100ms
* If you chain with other services (API Gateway, CloudFront, ALB, Lambda, SQS, Step Functions...), add their latencies as well
* X-Ray can help visualize the end-to-end latency

### Diagram
[<img src="https://i.imgur.com/rRrSiqj.png">](https://i.imgur.com/rRrSiqj.png)

--

## Security
* IAM Roles for Lambda to grant access to other AWS services
* **Resource-based Policies for Lambda** (Similar to S3 bucket policies):
  * Allow other accounts to invoke or manage Lambda
  * Allow other services to invoke or manage Lambda
* (define through the CLI):
````json
{
  "Sid": "sns",
  "Effect": "Allow",
  "Principal": {
    "Service": "sns.amazonaws.com"
  },
  "Action": "lambda:InvokeFunction",
  "Resource":
  "arn:aws:lambda:us-east-2:12345678012:function:my-function"
}
````

### Diagram
[<img src="https://i.imgur.com/mDHc73A.png">](https://i.imgur.com/mDHc73A.png)

---

## Lambda in a VPC
[<img src="https://i.imgur.com/pTxS8kJ.png">](https://i.imgur.com/pTxS8kJ.png)

---

## Logging, Monitoring & Tracing
* CloudWatch:
  * Lambda execution logs are stored in AWS CloudWatch Logs
  * Lambda metrics are displayed in CloudWatch Metrics (successfull invocations, error rate, latency, timeouts, etc...)
  * Make sure your Lambda function has an **execution role** with an IAM policy that authorized writes to CloudWatch Logs
* X-Ray:
  * It's possible to trace Lambda with X-Ray
  * Enable in Lambda configuration (runs the **X-Ray deamon** for you)
  * Use AWs SDK in Code
  * Ensure Lambda function has correct **IAM Execution Role**
  
---

## Synchronous Invocations (1/3)
* Synchronous: CLI, SDK, API Gateway
  * Results is returned right away
  * Error handling must happen client side (retries, **exponential backoff**, etc...)
  
### Diagram
[<img src="https://i.imgur.com/NmYJBud.png">](https://i.imgur.com/NmYJBud.png)

---

## Asynchronous Invocation (2/3)
* S3, SNS, CloudWatch Events...
* Lambda attempts to retry on errors (**3 tries total**)
* Make sure the processing is **idempotent** (in case of retries)
