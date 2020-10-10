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
    return "Success"
````

* Test :
    * demo-lambda-queue\send & receive message
    * Message body: this is a test for my Demo-SQS (Lambda)
    * message attribute
         * name: foo
         * type: string
         * value: bar
    * send message

[<img src="https://i.imgur.com/q6HnUah.png">](https://i.imgur.com/q6HnUah.png)

* Lambda\Monitoring\View in CW\log streams\
      * records
      * 
````log
{'Records': [{'messageId': 'd6221885-fd00-4e43-bcf4-da46176bbbd3', 'receiptHandle': 'AQEBf8HFBqPO4okHCAgKKz5n5Ooufh65J7TL/znOafEEvLdny/0waY32mkR3dotLbV9PJQYazNN4hqgjWK5on+36M7uXPnfFBKy3VuOxKNsWnJUaE9Jw/MeTqbm3MOWO7z79ITxttiVjnNMFgHPbzFrY7Vtg16m78Mz3VAWug3E2J6atVGZkiPYudkFyqKjQf2ENOTG8lRx3zLJcQKZ99ZUTq+9EsLwNJoauZjXlnGKGR/n5PiTehicG+wzNvsxtnWbfxhPhLEj7q9aQSVSLAU2MZHI6ly11Z+ieRcsmjuJd+pLUn58F1XJv7FRmZS/vZMyNdTHiw/ooM3iWjHDBMLTIgnuyT4WUOlZfCwc2V6IIAKGfLVzOqGfQGX83Lem6tidf', 'body': 'long polling', 'attributes': {'ApproximateReceiveCount': '3', 'SentTimestamp': '1602120197746', 'SenderId': 'AIDAWG6XJ6ZASQMYJ3QHN', 'ApproximateFirstReceiveTimestamp': '1602120197748'}, 'messageAttributes': {}, 'md5OfBody': 'b9afa4b934adcb16f35b6be3653ab29b', 'eventSource': 'aws:sqs', 'eventSourceARN': 'arn:aws:sqs:us-east-1:427263915585:Demo-SQS', 'awsRegion': 'us-east-1'}]}
````

[<img src="https://i.imgur.com/zUG412v.png">](https://i.imgur.com/zUG412v.png)

* another message (SQS)
* message body: another test
* message attribute
      * name: troi
      * value: tes
      
* check out again in CW\log streams
      * body: another test
      * messageAttributes: troi
      * stringValue: test

````log
{'Records': [{'messageId': '810ae51c-6c60-4bfa-8059-579d405a56fb', 'receiptHandle': 'AQEB4ebw15dO/jXkWgTPyRYl340gE9Mrznn60x0sIrgUZSx4cm/LLO0qZ5OPlk/Uu8A5xej0ZxAbWiwUohqCzu3OHNKi1XGtIPbvi7WkIFRxbpKviLsXkNvinUkAxJQIUBQTEJrtSQE7P9tTfRBmeoJd/d8Qi0oK5GFGnej7vl8fGFswNhIRGNC9qMuanJZFi+JljwwddL6MMvU82bJSlsJrCWbUcXh/MRx08rUdqK5Rzo++sQtyc7/beyY2IaTI3PkwO25kkNhNyFiIImk3ahqgvxnfw68dQNKxjfOW6G4uP9v0M5b8rrIstjiKASgvpyYh3E6m8J3/WMnVJMKmQn+NbIX/2HZwgFHlZgEmnqebAoAyDDO+wmtFV7wQHF3UYOJD', 'body': 'another test', 'attributes': {'ApproximateReceiveCount': '1', 'SentTimestamp': '1602289682761', 'SenderId': 'AIDAWG6XJ6ZASQMYJ3QHN', 'ApproximateFirstReceiveTimestamp': '1602289682775'}, 'messageAttributes': {'troi': {'stringValue': 'test', 'stringListValues': [], 'binaryListValues': [], 'dataType': 'String'}}, 'md5OfBody': '5e8862cd73694287ff341e75c95e3c6a', 'md5OfMessageAttributes': '34b292dc1c51dab605482df5e1678a64', 'eventSource': 'aws:sqs', 'eventSourceARN': 'arn:aws:sqs:us-east-1:427263915585:Demo-SQS', 'awsRegion': 'us-east-1'}]}
````

[<img src="https://i.imgur.com/YnUj50g.png">](https://i.imgur.com/YnUj50g.png)
[<img src="https://i.imgur.com/7X3cnRz.png">](https://i.imgur.com/7X3cnRz.png)

* SQS\Message available: **zero message**
* the message was successfully processed by lambda & then deleted from the queue

[<img src="https://i.imgur.com/O2mC19C.png">](https://i.imgur.com/O2mC19C.png)

* Disable this mapping :

[<img src="https://i.imgur.com/FnDoPjh.png">](https://i.imgur.com/FnDoPjh.png)
[<img src="https://i.imgur.com/p5RrQCJ.png">](https://i.imgur.com/p5RrQCJ.png)
