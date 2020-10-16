# SAM API Gateway

## Acronym
* SAM - Serverless Application Model
* CF - CloudFormation

## Doc
* [serverless-app-examples](https://github.com/amazon-archives/serverless-app-examples/tree/master/python)

## Intro
* app.py:
````python
import boto3
import json
import os

print('Loading function')


def respond(err, res=None):
    return {
        'statusCode': '400' if err else '200',
        'body': err.message if err else json.dumps(res),
        'headers': {
            'Content-Type': 'application/json',
        },
    }


def lambda_handler(event, context):
    print("Received event: " + json.dumps(event, indent=2))
    respond(None,res="Test from SAM")
````

* template.yaml:
````yaml
# SAM FILE
AWSTemplateFormatVersion: '2010-09-09'
Transform: 'AWS::Serverless-2016-10-31'
Description: A starter AWS Lambda function.
Resources:
  helloworldpython3:
    Type: 'AWS::Serverless::Function'
    Properties:
      Handler: app.lambda_handler
      Runtime: python3.6
      CodeUri: SRC/
      Description: A starter AWS Lambda function.
      MemorySize: 128
      Timeout: 3
      Events:
       TestSAMAPI:
         Type: Api
         Properties:
           Path: /test
           Method: GET
````

* AWS CLI
    * package CF
````bash
aws cloudformation package \
--s3-bucket demo-01-code-sam \
--template-file template.yaml \
--output-template-file gen/template-generated.yaml
````
[<img src="https://i.imgur.com/xRti6pO.png">](https://i.imgur.com/xRti6pO.png)

* check up our generated-template.yaml
    * CodeUri
      * s3 url was not updated !?
      
* deploy
````bash
aws cloudformation deploy \
--template-file gen/template-generated.yaml \
--stack-name demo-sam \
--capabilities CAPABILITY_IAM
````

[<img src="https://i.imgur.com/t8uAuN6.png">](https://i.imgur.com/t8uAuN6.png)

* faled 
    * create lambda
    
[<img src="https://i.imgur.com/5BL2A2o.png">](https://i.imgur.com/5BL2A2o.png)
[<img src="https://i.imgur.com/e7xxwwk.png">](https://i.imgur.com/e7xxwwk.png)
