# Demo - Kinesis Data Streams

## Anocrym
* CW - CloudWatch

## Lambda - Producer
* Runtime: Python 3.8
* Lambda name function: Producer
* SRC:
````python
import json
import boto3
import os
import random
import string

client = boto3.client("kinesis")
stream_name = os.getenv("STREAM_NAME", False)

def randomString(stringLength=10);
  """Generate a random string of fixed length """
  letters = string.ascii_lowercase
  return "".join(random.choice(letters) for i in range(stringLength))

def lambda_handler(event, context):
  i = 0
  while i < 21:
    string = randomString(15)
    print(f'Putting this data int oteh stream: {string}')
    client.put_record(
      StreamName=stream_name, Data=String, PartitionKey="PluralSight"
    )
    I += 1
````
[<img src="https://i.imgur.com/vOtx3hb.png">](https://i.imgur.com/vOtx3hb.png)

---

## Env var
* Key: STREAM_NAME
* Value: pluralsightStream

---

## Lambda - Consumer
* Designer
  * Trigger
    * Kinesis
    
[<img src="https://i.imgur.com/8OkG8z0.png">](https://i.imgur.com/8OkG8z0.png)
[<img src="https://i.imgur.com/gPDsF4y.png">](https://i.imgur.com/gPDsF4y.png)
[<img src="https://i.imgur.com/L4nZBlV.png">](https://i.imgur.com/L4nZBlV.png)
    
* Function code:
````py
import json
import boto3
import os
import time

client = boto3.client("kinesis")

def lambda_handler(event, context):
  record = event["Records"][0]["kinesis"]["dataq"]
  print(event)
  print(record)
  partion_key = event["Records"][0]["partionkey"]
  print(partion_key)
````
[<img src="https://i.imgur.com/HIcwOEG.png">](https://i.imgur.com/HIcwOEG.png)

---

## Test
* Lambda function: Producer
  * test
  
[<img src="https://i.imgur.com/1iC9BpI.png">](https://i.imgur.com/1iC9BpI.png)

---

## CloudWatch
* Lambda\consumer\view logs in CW
  * Log Stream\

[<img src="https://i.imgur.com/ul1qZtz.png">](https://i.imgur.com/ul1qZtz.png)
[<img src="https://i.imgur.com/8k0PzyC.png">](https://i.imgur.com/8k0PzyC.png)
