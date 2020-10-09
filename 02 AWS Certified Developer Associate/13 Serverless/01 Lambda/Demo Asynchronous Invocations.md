# Demo Asynchronous Invocations

## Doc

## Acronym
* CW - CloudWatch
* DLQ - Dead Letter Queue
* SQS - Simple Queue Service
* IAM - Identity & Access Management

## Intro
* code in Lambda:
````python
import json

print('Loading function')


def lambda_handler(event, context):
    #print("Received event: " + json.dumps(event, indent=2))
    print("value1 = " + event['key1'])
    print("value2 = " + event['key2'])
    print("value3 = " + event['key3'])
    return event['key1']  # Echo back the first key value
    #raise Exception('Something went wrong')
````
* AWS CLI
* this is an **asynchronous.sh** invocation:
    * --invocation-type Event -this corresponds to an synchronous invocation for Lambda
````bash
aws lambda invoke --function-name Demo-Lambda \
--cli-binary-format raw-in-base64-out \
--payload '{"key1": "value1", "key2": "value2", "key3": "value3" }' \
--invocation-type Event \
--region us-east-1 response.json
````
[<img src="https://i.imgur.com/JINVXT0.png">](https://i.imgur.com/JINVXT0.png)

* Lambda\Demo-Lambda\Monitoring\view CW

[<img src="https://i.imgur.com/rnkFSOu.png">](https://i.imgur.com/rnkFSOu.png)

* CW\recent\log streams

[<img src="https://i.imgur.com/VgBBqKh.png">](https://i.imgur.com/VgBBqKh.png)

* make failed (for demo)
* Lambda code:
* comment return
* uncomment raise

[<img src="https://i.imgur.com/sOK24M7.png">](https://i.imgur.com/sOK24M7.png)
[<img src="https://i.imgur.com/TCeRGEU.png">](https://i.imgur.com/TCeRGEU.png)

* buttom console Lambda\**Asynchronous invocation**
* edit

[<img src="https://i.imgur.com/R3ZULhU.png">](https://i.imgur.com/R3ZULhU.png)

* Retries
    * Maximum age of event: 6h
    * Retry attemps: 2
    * DLQ: SQS
    * Queue: Demo-DLQ
    
[<img src="https://i.imgur.com/RpJ4hp4.png">](https://i.imgur.com/RpJ4hp4.png)

* IAM\Role\Demo-Lambda

[<img src="https://i.imgur.com/DWJxh7c.png">](https://i.imgur.com/DWJxh7c.png)

* Attach policies\
* filter policies: SQS
* take : AmazonSQSFullAccess (over provision)

[<img src="https://i.imgur.com/GKfFkV6.png">](https://i.imgur.com/GKfFkV6.png)
[<img src="https://i.imgur.com/llZPxjM.png">](https://i.imgur.com/llZPxjM.png)

* Retry to save "Edit asynchronous configuration"

[<img src="https://i.imgur.com/K6t8Vlc.png">](https://i.imgur.com/K6t8Vlc.png)

* we want a trigger failure
* SQS\zero message

[<img src="https://i.imgur.com/eTbs4Dm.png">](https://i.imgur.com/eTbs4Dm.png)

* AWS CLI
* invoke againt lambda function asynchronously

[<img src="https://i.imgur.com/ZTNdpdg.png">](https://i.imgur.com/ZTNdpdg.png)

* wait ~3 min
* refresh SQS
* message id\body

[<img src="https://i.imgur.com/zEjqOqB.png">](https://i.imgur.com/zEjqOqB.png)
[<img src="https://i.imgur.com/g7b64fC.png">](https://i.imgur.com/g7b64fC.png)

* roll back edit code Demo-Lambda

[<img src="https://i.imgur.com/SmbUEFJ.png">](https://i.imgur.com/SmbUEFJ.png)
[<img src="https://i.imgur.com/9eVerWw.png">](https://i.imgur.com/9eVerWw.png)

* view in CW\log group\recent\log streams
* failed 3 times with same ID

[<img src="https://i.imgur.com/KVRh0kL.png">](https://i.imgur.com/KVRh0kL.png)
