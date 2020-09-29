# S3 Event Notifications

## Acronym
* SNS - Simple Notification Service
* SQS - Simple queue service
* ARN - Amazon resource Name

## Doc

## URLs
* [AWS Policy Generator](https://awspolicygen.s3.amazonaws.com/policygen.html)

## Intro
* S3:ObjectCreated, S3:ObjectRemoved, S3:ObjectRestore, S3:Replication...
* Object name filtering possible (*.jpg)
* <ins>Use case:</ins> generate thumbnails of images uploaded to S3
* Can create as my "S3 events" as desired
* S3 event notifications typically deliver events in seconds but can sometimes take a minute or longer
* If two writes are made to a single non-versioned object at the same time, it's possible that only a single event
  notification will be sent
* If you want to ensure that an event notifiction is sent for every successful write, you can enable versioning on your bucket

### Diagram
[<img src="https://i.imgur.com/4rXIioa.png">](https://i.imgur.com/4rXIioa.png)

---

## Demo
````bash
aws s3 mb s3://demo-01-event-notification
aws s3api put-bucket-versioning --bucket demo-01-event-notification \
  --versioning-configuration Status=Enabled
````

* S3\MyBucket\Properties\Events\Add notification:

[<img src="https://i.imgur.com/S3T6nAO.png">](https://i.imgur.com/S3T6nAO.png)

* Setup SQS\Create queue:
    * Name: demo-s3-event
    * RadioButton: Std --ensure that your bucket & SQS are same Region
    * Create queue
    
[<img src="https://i.imgur.com/yNkS0SN.png">](https://i.imgur.com/yNkS0SN.png)

* Copy: ARN

[<img src="https://i.imgur.com/iwwF5tX.png">](https://i.imgur.com/iwwF5tX.png)

* Back S3\New Event:

[<img src="https://i.imgur.com/hx2zWAJ.png">](https://i.imgur.com/hx2zWAJ.png)

* error
````text
Unable to validate the following destination configurations.
Permissions on the destination queue do not allow S3 to publish notifications from 
this bucket. (arn:aws:sqs:ca-central-1:427263915585:demo-s3-event)
````

[<img src="https://i.imgur.com/2hbM2dm.png">](https://i.imgur.com/2hbM2dm.png)

* Go to our_new_SQS\permissions
* You can used Policy generator
````json
{
  "Version": "2012-10-17",
  "Id": "Policy1601390762048",
  "Statement": [
    {
      "Sid": "Stmt1601390757645",
      "Effect": "Allow",
      "Principal": "*",
      "Action": "sqs:SendMessage",
      "Resource": "arn:aws:sqs:ca-central-1:427263915585:demo-s3-event"
    }
  ]
}
````
[<img src="https://i.imgur.com/WYW5pAD.png">](https://i.imgur.com/WYW5pAD.png)

### Test
* upload a new file
````bash
aws s3 cp mini_colley.jpg s3://demo-01-event-notification
````
[<img src="https://i.imgur.com/LzFqFvL.png">](https://i.imgur.com/LzFqFvL.png)

* SQS\Message Available:

[<img src="https://i.imgur.com/FTWa0gu.png">](https://i.imgur.com/FTWa0gu.png)


* Action\receive message:

[<img src="https://i.imgur.com/tLamBDY.png">](https://i.imgur.com/tLamBDY.png)

* Poll for messages:

[<img src="https://i.imgur.com/2OtOLU5.png">](https://i.imgur.com/2OtOLU5.png)

* 1st message (test):

[<img src="https://i.imgur.com/1yr7tTR.png">](https://i.imgur.com/1yr7tTR.png)

* 2nd message (upload):

[<img src="https://i.imgur.com/KlaKQqR.png">](https://i.imgur.com/KlaKQqR.png)

````bash
# upload another file
aws s3 cp beach.jpeg s3://demo-01-event-notification
````

[<img src="https://i.imgur.com/a3GGmqH.png">](https://i.imgur.com/a3GGmqH.png)
[<img src="https://i.imgur.com/MacktHX.png">](https://i.imgur.com/MacktHX.png)
[<img src="https://i.imgur.com/dX3upES.png">](https://i.imgur.com/dX3upES.png)
