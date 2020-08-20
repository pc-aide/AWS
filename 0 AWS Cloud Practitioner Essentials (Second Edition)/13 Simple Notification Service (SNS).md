# Simple Notification Service (SNS)

## Video
* [Introduction to Amazon Simple Notification Service (SNS)](https://www.aws.training/Details/Video?id=15881)

## Errors
### [New Event(S3)](https://i.imgur.com/qptgj4u.png)
* Unable to validate the following destination configurations. Permissions on
  the destination topic do not allow S3 to publish notifications from this bucket.
  (arn:aws:sns:us-east-2:11111111111:SNSDemo01)

## Doc
* [What is Amazon SNS?](https://docs.aws.amazon.com/sns/latest/dg/welcome.html)
* [How do I avoid the error "Unable to validate the following destination configurations" when using S3 event notifications in AWS CloudFormation?](https://aws.amazon.com/premiumsupport/knowledge-center/unable-validate-destination-s3/)

## Acronym
* SNS - Simple Notification Service

## Introduction
[<img src="https://i.imgur.com/bccE7oC.png">](https://i.imgur.com/bccE7oC.png)

## What is SNS?
1) Flexible, fully managed pub/sub messaging & mobile communications service

2) Coordinates the delivery of messages to subscribing endpoints & clients

3) Easy to setup, operate & send reliable communications

4) Decouple & scale microservices, distributed systems & serverless applications

[<img src="https://i.imgur.com/00tyTxb.png">](https://i.imgur.com/00tyTxb.png)

## E.g.
* AWS Console\Services\SNS\Tpics

[<img src="https://i.imgur.com/PNbzfIV.png">](https://i.imgur.com/PNbzfIV.png)

* Create topic

[<img src="https://i.imgur.com/mnEKka5.png">](https://i.imgur.com/mnEKka5.png)

* create subscription (who receive SNS)

[<img src="https://i.imgur.com/nhb5TnK.png">](https://i.imgur.com/nhb5TnK.png)

[<img src="https://i.imgur.com/kHmEoth.png">](https://i.imgur.com/kHmEoth.png)

[<img src="https://i.imgur.com/nfuGfZm.png">](https://i.imgur.com/nfuGfZm.png)

[<img src="https://i.imgur.com/BDxZwgD.png">](https://i.imgur.com/BDxZwgD.png)

* S3\<BucketName\>\Properties\Event\Add noti.

[<img src="https://i.imgur.com/RXh5zAT.png">](https://i.imgur.com/RXh5zAT.png)
