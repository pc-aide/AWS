# SAM DynamoDB

## Acronym
* SAM - Serverless Application Model
* CF - CloudFormation

## Doc
* [Serverless App Examples](https://github.com/amazon-archives/serverless-app-examples/tree/master/python)
    1. lambda_function.py
    2. template.yaml
* [SAM](https://github.com/aws/serverless-application-model/blob/master/versions/2016-10-31.md)
    1. search: **SimpleTable** - no cost

## Intro
* app.py:
````python
import boto3
import json
import os

print('Loading function')

# create the client outside of the handler
region_name = os.environ['REGION_NAME']
dynamo = boto3.client('dynamodb', region_name=region_name)
table_name = os.environ['TABLE_NAME']

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
    scan_result = dynamo.scan(TableName=table_name)
    return respond(None, res=scan_result)
````

* template.yaml
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
      Environment:
        Variables:
          TABLE_NAME: !Ref: Table
          REGION_NAME: !Reg AWS::Region
      Events:
       TestSAMAPI:
         Type: Api
         Properties:
           Path: /test
           Method: GET
      Policies:
        - DynamoDBCrudPolicy:
            TableName: !Ref Table

  Table:
   Type: AWS::Serverless::SimpleTable
   Properties: 
    PrimaryKey:
      Name: greeting
      Type: String
    ProvisionedThroughput:
      ReadCapacityUnits: 2
      WriteCapacityUnits: 2
````

* package CF:
````bash
aws cloudformation package \
--s3-bucket demo-01-code-sam \
--template-file template.yaml \
--output-template-file \
gen/template-generated.yaml
````
[<img src="https://i.imgur.com/fZd02YQ.png">](https://i.imgur.com/fZd02YQ.png)

* deploy
````bash
aws cloudformation deploy \
--template-file gen/template-generated.yaml \
--stack-name demo-sam --capabilities CAPABILITY_IAM
````
[<img src="https://i.imgur.com/sxZkBUI.png">](https://i.imgur.com/sxZkBUI.png)
