# Demo - Pub/Sub

## URL
* https://www.mailinator.com/

## Acronym
* CW - CloudWatch
* Pu/Sub - Publishier/Subcriber

---

## Steps

### 01 - SNS
* Create a topic std
* Name: SNS

[<img src="https://i.imgur.com/tiKitht.png">](https://i.imgur.com/tiKitht.png)

* Create subscription
  * Protocol: email
  * endpoint: testawssns@mailinator.com
  
[<img src="https://i.imgur.com/FhPl3IG.png">](https://i.imgur.com/FhPl3IG.png)

* Status Pending confirmation

[<img src="https://i.imgur.com/wBLq06Y.png">](https://i.imgur.com/wBLq06Y.png)

* Confirm subscription

[<img src="https://i.imgur.com/YRynfPK.png">](https://i.imgur.com/YRynfPK.png)
[<img src="https://i.imgur.com/K9mXxSP.png">](https://i.imgur.com/K9mXxSP.png)

* Confirmed

[<img src="https://i.imgur.com/HJl09dm.png">](https://i.imgur.com/HJl09dm.png)

---

## 02 - 2x SQS{A,B} std
* Create 2x SQS std
  1) Name: SQSA & SQS B
  
[<img src="https://i.imgur.com/6F9SOOJ.png">](https://i.imgur.com/6F9SOOJ.png)

* SQSA\Subcribe to Amazon SNS Topics

[<img src="https://i.imgur.com/nuDs5aV.png">](https://i.imgur.com/nuDs5aV.png)
[<img src="https://i.imgur.com/o4YZS1k.png">](https://i.imgur.com/o4YZS1k.png)
[<img src="https://i.imgur.com/qI7oUFS.png">](https://i.imgur.com/qI7oUFS.png)

* SQSA\Access policy
  * update automatic
    * topic-subcription
    * action: SendMessage
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
      "Action": "SQS:*",
      "Resource": "arn:aws:sqs:ca-central-1:427263915585:SQSA"
    },
    {
      "Sid": "topic-subscription-arn:aws:sns:ca-central-1:427263915585:SNS",
      "Effect": "Allow",
      "Principal": {
        "AWS": "*"
      },
      "Action": "SQS:SendMessage",
      "Resource": "arn:aws:sqs:ca-central-1:427263915585:SQSA",
      "Condition": {
        "ArnLike": {
          "aws:SourceArn": "arn:aws:sns:ca-central-1:427263915585:SNS"
        }
      }
    }
  ]
}
````
[<img src="https://i.imgur.com/aMw680K.png">](https://i.imgur.com/aMw680K.png)

* SNS\Refresh
  * New sub\SQSA
  
[<img src="https://i.imgur.com/7TuGHBi.png">](https://i.imgur.com/7TuGHBi.png)

* You can't from SNS\Subscription\SQS - it will fail (access policy from SQS)
* we need from SQS\Subscription to SNS but not the reverse !

* SQSB\Subcription SNS:
  * update access policy
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
      "Action": "SQS:*",
      "Resource": "arn:aws:sqs:ca-central-1:427263915585:SQSB"
    },
    {
      "Sid": "topic-subscription-arn:aws:sns:ca-central-1:427263915585:SNS",
      "Effect": "Allow",
      "Principal": {
        "AWS": "*"
      },
      "Action": "SQS:SendMessage",
      "Resource": "arn:aws:sqs:ca-central-1:427263915585:SQSB",
      "Condition": {
        "ArnLike": {
          "aws:SourceArn": "arn:aws:sns:ca-central-1:427263915585:SNS"
        }
      }
    }
  ]
}
````

[<img src="https://i.imgur.com/56Jkd6Y.png">](https://i.imgur.com/56Jkd6Y.png)
[<img src="https://i.imgur.com/zzq2TnR.png">](https://i.imgur.com/zzq2TnR.png)

* SNS\Subscriptions
  * SQSB
  
[<img src="https://i.imgur.com/up0pXSq.png">](https://i.imgur.com/up0pXSq.png)

* SNS\SQS{A,B}\**Enable Raws message delivery**
  * Raws message delivery
    * no formatage with data, send exact format that we specify

[<img src="https://i.imgur.com/hrrnkoH.png">](https://i.imgur.com/hrrnkoH.png)
[<img src="https://i.imgur.com/cw2f8OO.png">](https://i.imgur.com/cw2f8OO.png)
[<img src="https://i.imgur.com/wAQHDkc.png">](https://i.imgur.com/wAQHDkc.png)

---

### 03 - 2x Lambda
* Create new lambdaA:
  * Name: LambdaWorkerA
  * Runtime: python 3.8
  * code
````py
import json

def lambda_handler(event, context):
    number = int(event['Records'][0]['body'])
    print(f'Lambda Function A ---> {number +1} ')
    return event
````

* Permissions
  * Create the policy if not exist or attach the policy
  * Name (policy) : LambdaAllowWorkerA
  * code
````json
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
            "Resource": "arn:aws:sqs:ca-central-1:427263915585:SQSA"
        }
    ]
}
````

[<img src="https://i.imgur.com/AhmOsrm.png">](https://i.imgur.com/AhmOsrm.png)
[<img src="https://i.imgur.com/Ky8HDRH.png">](https://i.imgur.com/Ky8HDRH.png)
[<img src="https://i.imgur.com/CIeidBt.png">](https://i.imgur.com/CIeidBt.png)
[<img src="https://i.imgur.com/7DS29D7.png">](https://i.imgur.com/7DS29D7.png)

* Add triggers
  * Select a trigger: SQS
  * SQS queue: SQSA
  * Batch size: 1

[<img src="https://i.imgur.com/SMAT3xy.png">](https://i.imgur.com/SMAT3xy.png)
[<img src="https://i.imgur.com/6vbeUJJ.png">](https://i.imgur.com/6vbeUJJ.png)
[<img src="https://i.imgur.com/tkowqqD.png">](https://i.imgur.com/tkowqqD.png)

* Create newLambdaB
  * Name: LambdaWorkerB
  * Runtime: Python 3.8
  * code
````py
import json

def lambda_handler(event, context):
    number = int(event['Records'][0]['body'])
    print(f'Lambda Function B ---> {number * 100} ')
    return event
````
[<img src="https://i.imgur.com/kLNWh2f.png">](https://i.imgur.com/kLNWh2f.png)

* Permission idem 
* Name.policy: LambdaAllowWorkerB
* code
````json
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
            "Resource": "arn:aws:sqs:ca-central-1:427263915585:SQSB"
        }
    ]
}
````
[<img src="https://i.imgur.com/XIvpuHo.png">](https://i.imgur.com/XIvpuHo.png)

* LambdaWorkerB\Add trigger
  * Select trigger: SQS
  * Name : SQSB
  * Batch size: 1
  
[<img src="https://i.imgur.com/QedrQC5.png">](https://i.imgur.com/QedrQC5.png)
[<img src="https://i.imgur.com/hNUYUri.png">](https://i.imgur.com/hNUYUri.png)

---

### 04 - Test Publish message to topic
* SNS\Publish message
  * body
    * 5
  * publish message

[<img src="https://i.imgur.com/TTHwaDe.png">](https://i.imgur.com/TTHwaDe.png)
[<img src="https://i.imgur.com/8XShoe4.png">](https://i.imgur.com/8XShoe4.png)

* Message delivery 3x subs

[<img src="https://i.imgur.com/VUnqrdm.png">](https://i.imgur.com/VUnqrdm.png)

* email\New message receive:

[<img src="https://i.imgur.com/1n3zTkC.png">](https://i.imgur.com/1n3zTkC.png)

* LambdaWorkerA\Monitoring\CW\log streams
  * log events
````log
2021-01-22T21:08:38.524-05:00

Lambda Function A ---> 6 
Lambda Function A ---> 6
````

[<img src="https://i.imgur.com/lNTboBt.png">](https://i.imgur.com/lNTboBt.png)
[<img src="https://i.imgur.com/e29zWhi.png">](https://i.imgur.com/e29zWhi.png)

* idem for LambdaWorkerB\Monitoring\CW\Log Streams
  * log events
````log
2021-01-22T21:08:38.508-05:00

Lambda Function B ---> 500 
Lambda Function B ---> 500
````

[<img src="https://i.imgur.com/nRXzjkh.png">](https://i.imgur.com/nRXzjkh.png)
