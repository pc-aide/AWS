# Creating first SAM Project

## Doc
* [serverless-app-examples](https://github.com/amazon-archives/serverless-app-examples/tree/master/python)

## Acronym

## Intro
* help
    * Initializes a new SAM project using custom template in a GIT/Mercurial repository
````bash
sam init --help
````
[<img src="https://i.imgur.com/Xq4arof.png">](https://i.imgur.com/Xq4arof.png)

* Folder structure
    * SAM/ folder
    * SAM/{template.yaml,commands.sh} files
      * SAM/SRC/ folder
        * SAM/SRC/app.py file
* app.py (from the doc):
````python
import json

print('Loading function')

def lambda_handler(event, context):
    #print("Received event: " + json.dumps(event, indent=2))
    return "Test SAM"  
````
* template.yaml (from doc):
      * Handler: NameFile.Function
      * CodeUri: src - folder
````yaml
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
