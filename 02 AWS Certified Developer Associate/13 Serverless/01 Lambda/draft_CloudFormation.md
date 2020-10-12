# CloudFormation

## Acronym
* CF - CloudFormation

## doc

## Intro 
### Inline
* we can use CF to upload Lambda function
* we have two ways:
    1) Inline:
* Inline functions are very simple
* Use the **Code.ZipFile** property
* You can't include function dependencies with inline functions
* Code:
````yaml
AWSTemplateFormation: "2010-09-09"
Description: Lambda function inline
Resource:
  primer:
    Typer: AWS::Lambda::Function
    Properties:
      Runtime: python3.x
      Role: arn:aws:iam::123456789012:role/lambda-role
      Handler: index.handler
      Code:
        ZipFile: |
          import os

          DB_URL = os.getenv("DB_URL")
          db_client = db.connect(DB_URL)
          def handler(event, context):
            user = db_client.get(user_id = event["user_id"])
            return user
````

### through S3
* You must store the Lambda zip in S3
* You must refer the S3 zip location in the CF code
        * S3Bucket
        * S3Key: full path to zip
        * S3ObjectVersion: if versioned bucket
* **if you update the code in S3, but don't update S3Bucket, S3key or S3ObjectVersion, CF won't update your function**
* Code:
````yaml
AWSTemplateFormationVersion: '2010-09-09'
Description: Lambda from S3
Resources:
  Function:
    Type: AWS::Lambda::Function
    Properties:
      Handler: index.handler
      Role: arn:aws:iam::123456789012:role/lambda-role
      Code:
        S3Bucket: my-bucket
        S3Key: function.zip
        S3ObjectVersion: String
      Runtime: nodejs12.x
````
Parameters:
  S3BucketParam:
    Type: String
  S3KeyParam:
    Type: String
  S3ObjectVersionParam:
    Type: String

Resources:
  LambdaExecutionRole:
    Type: AWS::IAM::Role
    Properties:
      AssumeRolePolicyDocument:
        Version: '2012-10-17'
        Statement:
        - Effect: Allow
          Principal:
            Service:
            - lambda.amazonaws.com
          Action:
          - sts:AssumeRole
      Path: "/"
      Policies:
      - PolicyName: root
        PolicyDocument:
          Version: '2012-10-17'
          Statement:
          - Effect: Allow
            Action:
            - logs:*
            Resource: arn:aws:logs:*:*:*
          - Effect: Allow
            Action:
            - xray:PutTraceSegments
            - xray:PutTelemetryRecords
            - xray:GetSamplingRules
            - xray:GetSamplingTargets
            - xray:GetSamplingStatisticSummaries
            Resource: "*"
          - Effect: Allow
            Action: 
            - s3:Get*
            - s3:List*
            Resource: "*"

  LambdaWithXRay: 
    Type: "AWS::Lambda::Function"
    Properties: 
      Handler: "index.handler"
      Role: 
        Fn::GetAtt: 
          - "LambdaExecutionRole"
          - "Arn"
      Code: 
        S3Bucket: 
          Ref: S3BucketParam
        S3Key: 
          Ref: S3KeyParam
        S3ObjectVersion:
          Ref: S3ObjectVersionParam
      Runtime: "nodejs12.x"
      Timeout: 10
      # Enable XRay
      TracingConfig:
        Mode: "Active"
---

## Demo
* lambda-xray.yaml:
````yml
Parameters:
  S3BucketParam:
    Type: String
  S3KeyParam:
    Type: String
  S3ObjectVersionParam:
    Type: String

Resources:
  LambdaExecutionRole:
    Type: AWS::IAM::Role
    Properties:
      AssumeRolePolicyDocument:
        Version: '2012-10-17'
        Statement:
        - Effect: Allow
          Principal:
            Service:
            - lambda.amazonaws.com
          Action:
          - sts:AssumeRole
      Path: "/"
      Policies:
      - PolicyName: root
        PolicyDocument:
          Version: '2012-10-17'
          Statement:
          - Effect: Allow
            Action:
            - logs:*
            Resource: arn:aws:logs:*:*:*
          - Effect: Allow
            Action:
            - xray:PutTraceSegments
            - xray:PutTelemetryRecords
            - xray:GetSamplingRules
            - xray:GetSamplingTargets
            - xray:GetSamplingStatisticSummaries
            Resource: "*"
          - Effect: Allow
            Action: 
            - s3:Get*
            - s3:List*
            Resource: "*"

  LambdaWithXRay: 
    Type: "AWS::Lambda::Function"
    Properties: 
      Handler: "index.handler"
      Role: 
        Fn::GetAtt: 
          - "LambdaExecutionRole"
          - "Arn"
      Code: 
        S3Bucket: 
          Ref: S3BucketParam
        S3Key: 
          Ref: S3KeyParam
        S3ObjectVersion:
          Ref: S3ObjectVersionParam
      Runtime: "nodejs12.x"
      Timeout: 10
      # Enable XRay
      TracingConfig:
        Mode: "Active"
````

* create a bucket
````bash
aws s3 mb s3://demo-cloudformation-lambda --regions us-east-1
````

* Enabled versioning
````bash
aws s3api put-bucket-versioning \
--bucket demo-cloudformation-lambda \
--versioning-configuration Status=Enabled
````

[<img src="https://i.imgur.com/iPLF1VN.png">](https://i.imgur.com/iPLF1VN.png)

* upload a zip file
````bash
aws s3 cp function.zip s3://demo-cloudformation-lambda
````

[<img src="https://i.imgur.com/FkeM8Nr.png">](https://i.imgur.com/FkeM8Nr.png)
[<img src="https://i.imgur.com/TS3Ipcm.png">](https://i.imgur.com/TS3Ipcm.png)

* CF\**Create stack**
        * Prepare template: Template is ready
        * Template source: Upload a template file
            * lambda-xray.yaml
            
[<img src="https://i.imgur.com/jgm8wD5.png">](https://i.imgur.com/jgm8wD5.png)

* Stack name: Lambda-Demo

[<img src="https://i.imgur.com/zX90xAZ.png">](https://i.imgur.com/zX90xAZ.png)
[<img src="https://i.imgur.com/IoQqMyH.png">](https://i.imgur.com/IoQqMyH.png)
[<img src="https://i.imgur.com/OWe6eTj.png">](https://i.imgur.com/OWe6eTj.png)

* Create stacks:

[<img src="https://i.imgur.com/xsFYj0r.png">](https://i.imgur.com/xsFYj0r.png)
[<img src="https://i.imgur.com/CYLCWPV.png">](https://i.imgur.com/CYLCWPV.png)

* failed
        * VersionID: bad
        * rollback
        
[<img src="https://i.imgur.com/wzxps9g.png">](https://i.imgur.com/wzxps9g.png)

* try again with good VersionID:

[<img src="https://i.imgur.com/75hb1IT.png">](https://i.imgur.com/75hb1IT.png)
[<img src="https://i.imgur.com/OCIt5Ey.png">](https://i.imgur.com/OCIt5Ey.png)

* Resources:
        * LambdaExecutionRole
        * LambdaWithXRay
        
[<img src="https://i.imgur.com/mpjFJRm.png">](https://i.imgur.com/mpjFJRm.png)

* Check out my new Lambda function:
        * Lambda-Demo-LambdaWithXRay-...

[<img src="https://i.imgur.com/EdEktDH.png">](https://i.imgur.com/EdEktDH.png)
[<img src="https://i.imgur.com/fHxwF4r.png">](https://i.imgur.com/fHxwF4r.png)

* we can test this function:
        * create new S3://cf-templates-...
        
[<img src="https://i.imgur.com/qxdHxjk.png">](https://i.imgur.com/qxdHxjk.png)
[<img src="https://i.imgur.com/KkiRS9Q.png">](https://i.imgur.com/KkiRS9Q.png)

* X-Ray

[<img src="https://i.imgur.com/P4UhXCt.png">](https://i.imgur.com/P4UhXCt.png)
