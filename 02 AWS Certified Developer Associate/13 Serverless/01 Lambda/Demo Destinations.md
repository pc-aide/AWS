# Demo Destinations

## Acronym
* SQS - Simple Queue Service

## Doc

## Intro
* Lambda\Demo-S3

[<img src="https://i.imgur.com/wH5KZ3X.png">](https://i.imgur.com/wH5KZ3X.png)

* Add destination
    * Source: Aynchronous invocation
    * Condition: On **failure**
    * Destination type: SQS queue
    * Destination: S3-Failure
    
Create queue (2x: success & failue)
1) Queue name: S3-**Failure**

[<img src="https://i.imgur.com/5cxHtSj.png">](https://i.imgur.com/5cxHtSj.png)
[<img src="https://i.imgur.com/SoXki8J.png">](https://i.imgur.com/SoXki8J.png)
[<img src="https://i.imgur.com/XgXqeSo.png">](https://i.imgur.com/XgXqeSo.png)
[<img src="https://i.imgur.com/FHIsP1u.png">](https://i.imgur.com/FHIsP1u.png)

* IAM Role (create automatic) for destination

[<img src="https://i.imgur.com/uefZDWR.png">](https://i.imgur.com/uefZDWR.png)
[<img src="https://i.imgur.com/J5czBy0.png">](https://i.imgur.com/J5czBy0.png)

* Add 2<sup>nd</sup> destination (**success**):
    * Source: Asynchronous invocation
    * Condition: On success
    * Destination type: SQS
    * Destination: S3-Success
    
[<img src="https://i.imgur.com/7khUJYe.png">](https://i.imgur.com/7khUJYe.png)
[<img src="https://i.imgur.com/GDlMcff.png">](https://i.imgur.com/GDlMcff.png)

* update IaM Role:

[<img src="https://i.imgur.com/yuz9Zvv.png">](https://i.imgur.com/yuz9Zvv.png)

* Test our function
    * S3\demo-01-events-lambda - upload a file:
````bash
aws s3 cp cat s3://demo-01-events-lambda
````

* we know it's successful
* check our S3-Success (SQS)
* view this message id

[<img src="https://i.imgur.com/HmHNK6i.png">](https://i.imgur.com/HmHNK6i.png)
[<img src="https://i.imgur.com/07IPW3T.png">](https://i.imgur.com/07IPW3T.png)
[<img src="https://i.imgur.com/gZfR7G0.png">](https://i.imgur.com/gZfR7G0.png)

* now test our **failure**
* Edit code Lambda (to return a error):
    * raise Exception('Something went wrong')
````python
import json

def lambda_handler(event, context):
    print(event)
    raise Exception('Something went wrong')
    return {
        'statusCode': 200,
        'body': json.dumps('Hello from Lambda!')
    }
````

* test again with another upload to S3:
````bash
aws s3 cp mini_colley.jpg s3://demo-01-events-lambda/
````

[<img src="https://i.imgur.com/4862ZBR.png">](https://i.imgur.com/4862ZBR.png)

* Check out our S3-Failure (SQS):
    * Messages available: **zero**
    * because we are in an asynchronous type of invocation
    * we'll do **three retries**
    * wait **~3min** to see that message
    * refresh\message avaialble: 1
    * message id (to see this body)
        * "condition": "RetriesExhausted"
    
[<img src="https://i.imgur.com/rWwP8Ze.png">](https://i.imgur.com/rWwP8Ze.png)
[<img src="https://i.imgur.com/xSukBCd.png">](https://i.imgur.com/xSukBCd.png)
[<img src="https://i.imgur.com/7znSiKp.png">](https://i.imgur.com/7znSiKp.png)
[<img src="https://i.imgur.com/xnpZHnT.png">](https://i.imgur.com/xnpZHnT.png)
