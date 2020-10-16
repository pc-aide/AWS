# Deploying SAM Project

## Doc

## Acronym
* CF - CloudFormation

## Intro
* commands.sh:
````shell
# Create a s3 bucket
aws s3 mb s3://demo-01-code-sam

# Package CloudFormation
aws cloudformation package \
--s3-bucket demo-01-code-sam \
--template-file template.yaml \
--output-template-file gen/template-generate.yaml

# sam package ...

````
[<img src="https://i.imgur.com/St6rv29.png">](https://i.imgur.com/St6rv29.png)
[<img src="https://i.imgur.com/QOVbUHJ.png">](https://i.imgur.com/QOVbUHJ.png)

* app.py
````bash

````

* overview the template-generate.yaml:
    * the same except CodeUri => ref s3 & update file
````yaml
AWSTemplateFormatVersion: '2010-09-09'
Transform: AWS::Serverless-2016-10-31
Description: A starter AWS Lambda function.
Resources:
  helloworldpython3:
    Type: AWS::Serverless::Function
    Properties:
      Handler: app.lambda_handler
      Runtime: python3.6
      CodeUri: s3://demo-01-code-sam/76cdb2bad9582d23c1f6f4d868218d6c
      Description: A starter AWS Lambda function.
      MemorySize: 128
      Timeout: 3
````
[<img src="https://i.imgur.com/zUajuEg.png">](https://i.imgur.com/zUajuEg.png)
[<img src="https://i.imgur.com/BXRQYZE.png">](https://i.imgur.com/BXRQYZE.png)

* deploy :
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

* failed
* Note: region: ca-central-ca for s3 & cloudformation

[<img src="https://i.imgur.com/JKjE8qg.png">](https://i.imgur.com/JKjE8qg.png)
[<img src="https://i.imgur.com/BfCAYAi.png">](https://i.imgur.com/BfCAYAi.png)
[<img src="https://i.imgur.com/ZZiY0zJ.png">](https://i.imgur.com/ZZiY0zJ.png)

* CF\Events
    * 

[<img src="https://i.imgur.com/aoL7lmR.png">](https://i.imgur.com/aoL7lmR.png)
