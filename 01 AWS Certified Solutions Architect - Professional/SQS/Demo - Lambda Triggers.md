# Demo - Lambda Triggers

## Steps
### 01 - SQS_Std
* Create sqs std with default value
* Access policy:
````json
{
  "Version": "2008-10-17",
  "Id": "__default_policy_ID",
  "Statement": [
    {
      "Sid": "__owner_statement",
      "Effect": "Allow",
      "Principal": {
        "AWS": "arn_user"
      },
      "Action": [
        "sqs:SendMessage",
        "sqs:DeleteMessage",
        "sqs:ReceiveMessage",
        "sqs:GetQueueAttributes"
      ],
      "Resource": "arn_sqs"
    }
  ]
}
````
* Dashboard :
[<img src="https://i.imgur.com/h8yufTd.png">](https://i.imgur.com/h8yufTd.png)

* Access policy:

[<img src="https://i.imgur.com/10FnsjE.png">](https://i.imgur.com/10FnsjE.png)
[<img src="https://i.imgur.com/9jrcrjT.png">](https://i.imgur.com/9jrcrjT.png)

---

### 02 - LambdaSender
* Lambda name: LambdaSender
* Runtime: Python 3.8
* Code:
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
[<img src="https://i.imgur.com/rPbrQ2m.png">](https://i.imgur.com/rPbrQ2m.png)

* Env var:
  * key: SQS_QUEUE
  * Value: <url_sqs>
[<img src="https://i.imgur.com/nDc9IM5.png">](https://i.imgur.com/nDc9IM5.png)

* Attach this policy to your Lambda:
  * Policy name: LambdaAllowSendMessageSQS
  * Code
````py
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Action": [
                "sqs:SendMessage"
            ],
            "Effect": "Allow",
            "Resource": "arn:aws:sqs:ca-central-1:427263915585:SQS_Sdt"
        }
    ]
}
````

[<img src="https://i.imgur.com/spQ29rL.png">](https://i.imgur.com/spQ29rL.png)
[<img src="https://i.imgur.com/slXnvdM.png">](https://i.imgur.com/slXnvdM.png)

* Test - send message
  * Check out our sqs\Receive message\body

[<img src="https://i.imgur.com/HWcZIiG.png">](https://i.imgur.com/HWcZIiG.png)
[<img src="https://i.imgur.com/UC7DGej.png">](https://i.imgur.com/UC7DGej.png)
[<img src="https://i.imgur.com/iED1BgE.png">](https://i.imgur.com/iED1BgE.png)

---

### 03 - LambdaWorker
* Goal
  * Delete **message in sqs_queue**
* Lambda name: LambdaWorker
* Runtime: python 3.8
* Code:
````py
import json

def lambda_handler(event, context):
    pretty_json = json.dumps(event, indent=2)
    print(pretty_json)
````
[<img src="https://i.imgur.com/IUw3PNt.png">](https://i.imgur.com/IUw3PNt.png)

* Permissions
  * Attach this policy: LambdaAllowDeleteMessage
  * code
````py
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Action": [
                "sqs:ReceiveMessage",
                "sqs:DeleteMessage",
                "sqs:GetQueueAttributes"
            ],
            "Effect": "Allow",
            "Resource": "arn:aws:sqs:ca-central-1:427263915585:SQS_Sdt"
        }
    ]
}
````
  
[<img src="https://i.imgur.com/P3huXEh.png">](https://i.imgur.com/P3huXEh.png)
[<img src="https://i.imgur.com/lq3SUQD.png">](https://i.imgur.com/lq3SUQD.png)

* Add trigger (lambda function)\sqs

[<img src="https://i.imgur.com/CGSo1Io.png">](https://i.imgur.com/CGSo1Io.png)
[<img src="https://i.imgur.com/wgE8KLg.png">](https://i.imgur.com/wgE8KLg.png)

### Test
* Test Receive Message, delete
* Go to the LambdaSender
  * Send at least 20 messages - delete messages (LambdaWorker very fast)
  * poll for message twice
  * second poll, all message will be delete (from LambdaWorker)
  
  
[<img src="https://i.imgur.com/Ct3Mvgj.png">](https://i.imgur.com/Ct3Mvgj.png)
[<img src="https://i.imgur.com/XWaTEZj.png">](https://i.imgur.com/XWaTEZj.png)
[<img src="https://i.imgur.com/oES4btZ.png">](https://i.imgur.com/oES4btZ.png)
