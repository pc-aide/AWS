# S3 Event Notifications

## Acronym
* SQS - Simple Queue Service
* SNS - Simple Notification Service
* DLQ - Dead Letter Queue
* CW - CloudWatch

## Doc

## Intro
* S3:ObjectCreated, S3:ObjectRemoved, S3:ObjectRestore, S3:Replication
* Object name filtering possible (*.jpg)
* <ins>Use case:</ins> generate thumbnails of images uploaded to S3
* S3 event notifications typically deliver events in seconds but can sometimes take a minutes or longer
* If two writes ar made to a single non-versioned object at the same time, it's possible that only a single event notification 
  will be sent
* If you want ot ensure that an event notification is sent for every successful wirte, you can enable versioning on your
  bucket

### Diagram
[<img src="https://i.imgur.com/zRbt97y.png">](https://i.imgur.com/zRbt97y.png)

---

## S3 Event Pattern - Metadata Sync
[<img src="https://i.imgur.com/fQ8Omn1.png">](https://i.imgur.com/fQ8Omn1.png)

---

## Demo
* Create new function
    * RadioButton: Author from scratch
    * function name: Demo-S3
    * Runtime: python
    * permissions: Create a new role with basic...
    
[<img src="https://i.imgur.com/ry7zRns.png">](https://i.imgur.com/ry7zRns.png)

* AWS CLI:
````bash
aws s3 mb s3://demo-01-events-lambda --region us-east-1
````
* Choose same region that our lambda-function for our bucket

* we want this bucket to rtigger my lambda function

* S3\properties\Events\ +add notification:
    * Name: Invoke-Lambda-NewObjects
    * Events: All object create events
    * Send to: : Lambda function
    * Lambda: Demo-S3
* Save

[<img src="https://i.imgur.com/GQG3dHL.png">](https://i.imgur.com/GQG3dHL.png)
[<img src="https://i.imgur.com/HaFe5V3.png">](https://i.imgur.com/HaFe5V3.png)

* Refresh Console Lambda\Designer
    * we can see the S3
    
[<img src="https://i.imgur.com/LNcmeSz.png">](https://i.imgur.com/LNcmeSz.png)

* Edit code lambda:
* add print(event):
````python
import json

def lambda_handler(event, context):
    print(event)
    return {
        'statusCode': 200,
        'body': json.dumps('Hello from Lambda!')
    }

````
* Lambda\Permissions
    * Resource-based policy
        * Effect: Allow
        * Service: S3...

[<img src="https://i.imgur.com/i3bHhcQ.png">](https://i.imgur.com/i3bHhcQ.png)

* Test to upload new file in our bucket
````bash
aws s3 cp beach.jpeg s3://demo-01-events-lambda
````

* Lambda\Monitoring\view in CW\log group\log streams
    * Region
    * eventName
    * InvokeLambdaOnNewObjects
    * key: beach.jped
* log:
````log
{'Records': [{'eventVersion': '2.1', 'eventSource': 'aws:s3', 'awsRegion': 'us-east-1', 'eventTime': '2020-10-09T19:23:46.254Z',
'eventName': 'ObjectCreated:Put', 'userIdentity': {'principalId': 'AWS:AIDAWG6XJ6ZASQMYJ3QHN'},
'requestParameters': {'sourceIPAddress': '199.36.223.194'}, 'responseElements': {'x-amz-request-id': 'FB2C084C406F8EE5',
'x-amz-id-2': 'CKb+hGAK/w54l+k6jp2E81EPE/sJlb7Z7gcghlK1kyKTqhqEZgxoUF39GqO5kYvnBIjKQp0kkqV7nz8TEJ+pqbWgKnxEXnCTtiV8KWaQwKY='},
's3': {'s3SchemaVersion': '1.0', 'configurationId': 'Invoke-Lambda-NewObjects',
'bucket': {'name': 'demo-01-events-lambda', 'ownerIdentity': {'principalId': 'A3PE565SRGGJUN'},
'arn': 'arn:aws:s3:::demo-01-events-lambda'}, 'object': {'key': 'beach.jpeg', 'size': 9309,
'eTag': '893a03214a368aa41a789df509628da7', 'sequencer': '005F80B8C32A671E56'}}}]}
````

[<img src="https://i.imgur.com/E6lhBI8.png">](https://i.imgur.com/E6lhBI8.png)
