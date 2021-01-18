# Demo - Lambda Triggers

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

client = boto3.client('sqs')
queue_url = os.environ['SQS_QUEUE']

def lambda_handler(event, context):
  client.send_message(
    QueueUrl=queue_url,
    MessageBody=f'Hello from Lambda! - Time: {time.time()}'
  )
````
[<img src="https://i.imgur.com/DtjmvS1.png>](https://i.imgur.com/DtjmvS1.png)
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
* ???

---

### 04 - Test
* Lambda\SQSSender\Test
  * Event name: test

[<img src="https://i.imgur.com/CrPSIbP.png">](https://i.imgur.com/CrPSIbP.png)
[<img src="https://i.imgur.com/Cl7nJPe.png">](https://i.imgur.com/Cl7nJPe.png)
[<img src="https://i.imgur.com/Llo1olc.png">](https://i.imgur.com/Llo1olc.png)
