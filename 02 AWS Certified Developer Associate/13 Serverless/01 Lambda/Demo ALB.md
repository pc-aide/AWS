# Demo ALB

## Acronym
* ALB - Application Load Balancer
* AZ - Availability Zone
* TG - Target Group
* CW - CloudWatch

## Doc
* [Using AWS Lambda with an Application Load Balancer](https://docs.aws.amazon.com/lambda/latest/dg/services-alb.html)

## Intro
* Lambda\create function
* RadioButton: Author from scratch
* Function name: Demo-ALB
* Runtime: Python
* Execution role: Create a new role with basic Lambda permissions
    * best practice to get one permission role by one lambda

[<img src="https://i.imgur.com/1V0mJSM.png">](https://i.imgur.com/1V0mJSM.png)
[<img src="https://i.imgur.com/4rb0XXU.png">](https://i.imgur.com/4rb0XXU.png)

* Create ALB:
    * name: Demo-lambda-ALB
    * AZs: least 3
    TG:
        * name: TGLambda
        * Target type: Lambda function
    Register Targets: Demo-ALB
    
[<img src="https://i.imgur.com/Va54Yqb.png">](https://i.imgur.com/Va54Yqb.png)
[<img src="https://i.imgur.com/LaZOPZe.png">](https://i.imgur.com/LaZOPZe.png)
[<img src="https://i.imgur.com/lZYzxCO.png">](https://i.imgur.com/lZYzxCO.png)

* Lambda\Edit code:
````python
import json

def lambda_handler(event, context):
    print(event)
    return {
        'statusCode': 200,
        'body': json.dumps('Hello from Lambda!')
    }
````
[<img src="https://i.imgur.com/khJIUYr.png">](https://i.imgur.com/khJIUYr.png)

* copied DNS name (ALB)
* Browswer

[<img src="https://i.imgur.com/lShaxC2.png">](https://i.imgur.com/lShaxC2.png)

* Edit lambda-code againt:
````python
{
    "statusCode": 200,
    "statusDescription": "200 OK",
    "isBase64Encoded": False,
    "headers": {
        "Content-Type": "text/html"
    },
    "body": "<h1>Hello from Lambda!</h1>"
}
````


[<img src="https://i.imgur.com/advWxZL.png">](https://i.imgur.com/advWxZL.png)

* F5 on Browswer

[<img src="https://i.imgur.com/FtwlNrn.png">](https://i.imgur.com/FtwlNrn.png)

* CloudWatch\log group\recent\log streams

[<img src="https://i.imgur.com/1Hwoq6E.png">](https://i.imgur.com/1Hwoq6E.png)
[<img src="https://i.imgur.com/QXejesv.png">](https://i.imgur.com/QXejesv.png)

* TG\Enabled: **Multi value headers**

[<img src="https://i.imgur.com/4mLAFO2.png">](https://i.imgur.com/4mLAFO2.png)

* Test Multi value headers
* with DNS Name:
````text
http://demo-lambda-alb-1013758342.us-east-1.elb.amazonaws.com/
````
* add this query & enter:
    * ?name=foo&name=bar
````text
http://demo-lambda-alb-1013758342.us-east-1.elb.amazonaws.com/?name=foo&name=bar
````
[<img src="https://i.imgur.com/WYs2m2j.png">](https://i.imgur.com/WYs2m2j.png)

* CW\log group\recent\log streams
    * multivalueQueryStringParameters
    * multivalueHeaders

[<img src="https://i.imgur.com/uyNyl7D.png">](https://i.imgur.com/uyNyl7D.png)

* Lambda\Permissions\

[<img src="https://i.imgur.com/zGVONc3.png">](https://i.imgur.com/zGVONc3.png)
