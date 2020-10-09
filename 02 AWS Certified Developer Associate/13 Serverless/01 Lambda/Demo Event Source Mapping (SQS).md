# Demo Event Source Mapping (SQS)

## Acronym
* SQS - Simple Queue Service

## Doc

## Intro
* Lambda\create funtion
    * RadioButton: Author from scrath
    * Function name: Demo-SQS
    * Runtime: python

[<img src="https://i.imgur.com/CpyKEm6.png">](https://i.imgur.com/CpyKEm6.png)

* SQS\Create queue
    * Queue Name: Demo-Lambda-Queue
    
[<img src="https://i.imgur.com/c16iyg5.png">](https://i.imgur.com/c16iyg5.png)

* Lambda\add trigger
    * Trigger: SQS
    * SQS queue: Demo-Lambda-Queue
    * Batch size: 10
        * min: 1
        * max: 10 - it's recommended for more messages
* Add

* Error:

[<img src="https://i.imgur.com/lZ3a098.png">](https://i.imgur.com/lZ3a098.png)

* Lambda\permissions\role name

[<img src="https://i.imgur.com/Qqj7Jpg.png">](https://i.imgur.com/Qqj7Jpg.png)

* Attach policies\AWSLambdaSQSQueueExecutionRole

[<img src="https://i.imgur.com/HDKrYYW.png">](https://i.imgur.com/HDKrYYW.png)

* try again to add trigger:

[<img src="https://i.imgur.com/NcbtgML.png">](https://i.imgur.com/NcbtgML.png)

* Edit code Lambda:
    * add print(event)
    * return success
````python
import json

def lambda_handler(event, context):
    print(event)
    return "Success""
````

* Test :
    * demo-lambda-queue\send & receive message
