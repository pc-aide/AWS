# Permissions - IAM Roles & Resource Policies

## Acronym
* IAM - Identity & Access Management
* CW - CloudWatch
* SQS - Simple Queue Service

## Doc

## Lambda Execution Role (IAM Role)
* Grants the Lambda function permissions to AWS services/resources
* Sample managed policies for Lambda:
    * AWSLambdaBasicExecutionRole - Upload logs to CW
    * AWSLambdaKinesisExecutionRole - Read from Kinesis
    * AWSLambdaDynamoDBExecutionRole - Read from DynamoDB Streams
    * AWSLambdaSQSQueueExecutionRole - Read from SQS
    * AWSLambdaVPCAccessExecutionRole - Deploy Lambda function in VPC
    * AWSXRayDaemonWriteAccess - Upload trace data to X-Ray
* When you use an <ins>event source mapping</ins> to invoke your function, Lambda uses the execution role to **read** event data
* Best practice: **create one Lambda Execution Role per function**

---

## Lmabda Resource Based Policies
* Use resource-based policies to give other accounts & AWS services permission to use your Lambda resources
* Similar to S3 bucket policies for S3 bucket
* An IAM principal can access Lambda:
    * if the IAM policy attached to the principal authorizes it (e.g. user access)
    * OR if the resource-based policy authorizes (e.g. service access)
* When an AWS service like S3 calls your Lambda function, the resource-based policy gives it access

---

## Demo
* IAM\Roles\
* search: Lambda

[<img src="https://i.imgur.com/Yverj8g.png">](https://i.imgur.com/Yverj8g.png)
[<img src="https://i.imgur.com/JmYXa2P.png">](https://i.imgur.com/JmYXa2P.png)
[<img src="https://i.imgur.com/zit4Vcg.png">](https://i.imgur.com/zit4Vcg.png)
[<img src="https://i.imgur.com/viPXu6A.png">](https://i.imgur.com/viPXu6A.png)
[<img src="https://i.imgur.com/QZbiExQ.png">](https://i.imgur.com/QZbiExQ.png)
[<img src="https://i.imgur.com/Hx0drBL.png">](https://i.imgur.com/Hx0drBL.png)

* Check out our functions:
    * Demo-S3
    * Demo-ALB
    * Demo-EventBridge - i delete the trigger (**invoke every minute**) so no resource-base policy
      * Resource-based policy
      
[<img src="https://i.imgur.com/KVIPnRJ.png">](https://i.imgur.com/KVIPnRJ.png)
[<img src="https://i.imgur.com/Q8QXQT6.png">](https://i.imgur.com/Q8QXQT6.png)
[<img src="https://i.imgur.com/wZqlNQd.png">](https://i.imgur.com/wZqlNQd.png)
