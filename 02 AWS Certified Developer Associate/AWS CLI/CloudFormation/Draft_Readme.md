# CloudFormation

## Switch
* aws cloudformation help

## Examples
### 01 package
* [`template.yaml`](#template.yaml)
````bash
aws cloudformation package \
--s3-bucket demo-01-code-sam \
--template-file template.yaml \
--output-template-file gen/template-generate.yaml
````
[<img src="https://i.imgur.com/QOVbUHJ.png">](https://i.imgur.com/QOVbUHJ.png)

### template.yaml
* [`app.py`](#app.py)
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
````

### 02 Deploy
````bash
aws cloudformation deploy \
--template-file gen/template-generate.yaml \
--stack-name test-sam
````
[<img src="https://i.imgur.com/IWND6mu.png">](https://i.imgur.com/IWND6mu.png)

* failed -> changeSet
    * CAPABILITY_IAM
* add the **capability flag**:
````bash
aws cloudformation deploy \
--template-file gen/template-generate.yaml \
--stack-name test-sam --capabilities CAPABILITY_IAM
````

### app.py
````python
import json

print('Loading function')

def lambda_handler(event, context):
    #print("Received event: " + json.dumps(event, indent=2))
    return "Test SAM"
````
