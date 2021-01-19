# Demo - Lambda Triggers

## Revision
* [19-01-2021]
  * Permission on sqs policy !?

## Steps
### 01 - SQS Std
* Create new SQS std with default values:

[<img src="https://i.imgur.com/lcwTdta.png">](https://i.imgur.com/lcwTdta.png)

----

### 02 - Lambda sender
* Create function:
  1) Lambda name: Sender | Runtime: Python 3.8
````py
import json
import boto3
import time
import os

client = boto3.client('sqs')
queue_url = os.environ['SQS_QUEUE']

def lambda_handler(event, context):
  client.send_message(
    QueueUrl=queue_url,
    MessageBody=f'Hello from Lambda! - Time: {time.time()}'
  )
````
[<img src="https://i.imgur.com/ABmBUte.png">](https://i.imgur.com/ABmBUte.png)
* Deploy
* Env var
  * Key
    * SQS_QUEUE
  * Value
    * <URL_SQS>
    
[<img src="https://i.imgur.com/lKgj3dG.png">](https://i.imgur.com/lKgj3dG.png)
[<img src="https://i.imgur.com/Mcnru2Z.png">](https://i.imgur.com/Mcnru2Z.png)


---

### 03 - Permissions (SendMessage)
* SQS\Policy
````json
{
  "Version": "2008-10-17",
  "Id": "__default_policy_ID",
  "Statement": [
    {
      "Sid": "__owner_statement",
      "Effect": "Allow",
      "Principal": {
        "AWS": "*"
      },
      "Action": [
        "SQS:SendMessage",
        "SQS:ReceiveMessage",
        "SQS:DeleteMessage",
        "SQS:GetQueueAttributes"
      ],
      "Resource": "arn_sqs"
    }
  ]
}
````

---

### 04 - Test-01
* Goal
  * Send message from Lambda sender
  * Check out receive message in sqs std
* Lambda\SQSSender\Test
  * Event name: test

[<img src="https://i.imgur.com/14MvSfB.png">](https://i.imgur.com/14MvSfB.png)

* Check out\SQS\Receive Messages
  * Send & receive messages

[<img src="https://i.imgur.com/V32A6Wt.png">](https://i.imgur.com/V32A6Wt.png)
[<img src="https://i.imgur.com/ifrKguK.png">](https://i.imgur.com/ifrKguK.png)

* Messages

[<img src="https://i.imgur.com/mSVH7yn.png">](https://i.imgur.com/mSVH7yn.png)

---

### 05 - Lambda Worker
* New Lambda function
  * Name: LambdaWorker
  * Runtime: Python 3.8
* Permission side sqs for worker
  * DeleteMessage
  * ReceiveMessage
  * GetQueueAttributes
* code:
````python
import json

def lambda_handler(event, context):
    pretty_json = json.dumps(event, indent=2)
    print(pretty_json)
````
[<img src="https://i.imgur.com/eeNCZc6.png">](https://i.imgur.com/eeNCZc6.png) 
* Add trigger

[<img src="https://i.imgur.com/o5fRGLp.png">](https://i.imgur.com/o5fRGLp.png)

* Trigger configuration
  * Select a trigger: SQS
  * SQS Name: <arn_sqs>
  * Batch size: 5
 
  
[<img src="https://i.imgur.com/6TZRONK.png">](https://i.imgur.com/6TZRONK.png)

* Permission
  * ReceiveMessage (sqs policy)

[<img src="https://i.imgur.com/fsZllye.png">](https://i.imgur.com/fsZllye.png)

* SQS std\Lambda triggers

