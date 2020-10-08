# SNS

## Acronym
* SNS - Simple Notificatin Service
* Pub/Sub - Publish subscribe
* SQS - Simple Queue Service
* ASG - Auto-Scaling Group
* SDK - Software Development Kit
* KMS - Key Management Service
* IAM - Identity & Access Management

## Doc

## Intro
* What if you want to send one message to many receivers?

### Diagram
[<img src="https://i.imgur.com/7FegWGF.png">](https://i.imgur.com/7FegWGF.png)

---

## SNS
* The "event producer" only sends message to one SNS topic  
* As many "event receivers" (subscriptions) as we want to listen to the SNS topic notifications
* Each subscriber to the topic will get all the messages (note: new feature to filter messages)
* Up to 10 millions subscribtions per topic
* 100k topics limit
* Subscribers can be:
    * SQS
    * HTTP/HTTPS (with delivery retries - how many times)
    * Lambda
    * Emails
    * SMS messages
    * Mobile Notifications
    
---

## SNS integrates with a lot of AWS services
* Many AWS services can send data directly to SNS for notifications
* CloudWatch (for alarms)
* ASGs notifications
* S3 (on bucket events)
* CloudFormation (upon state changes => failed to build, etc)
* Etc...

---

## SNS - How to publish
* Topic Publish (using the SDK)
    * Create a topic
    * Create a subscription (or many)
    * Publish to the topic
* Direct Publish (for mobile apps SDK)
    * Create a platform application
    * Create a platform endpoint
    * Publish to the platform endpoint
    * Works with Google GCM, Apple APNS, Amazon ADM...
    
---

## SNS - Security
* Encryption:
    * In-flight encryption using HTTPS API
    * At-rest encryption using KMS keys
    * Client-side encryption if the client wants to perform encryption/decryption itself
* Access Controls: IAM policies to regulate access to the SNS API
* SNS Access Policies (similar to S3 bucket policies)
    * Useful for cross-account access to SNS topics
    * Useful for allowing other service (S3...) to write to an SNS topic
