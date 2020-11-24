# Parameter Store

## Acronym
* SSM - System Manager
* IAM - Identity & Access Management

## Intro
* Secure storage for configuration & secrets
* Optional Seamless Encryption using KMS
* Serverless, scalable, durable, easy SDK, **free**
* Version tracking of configurations/secrets
* Configuration management using path & IAM
* Notifications with CloudWatch Events
* Integration with CloudFormation
  * Used **fn:ref** for example
* Can retrieve secrets from Secrets Manager using the SSM Parameter Store API
  
### Diagram
[<img src="https://i.imgur.com/a9VuOSz.png">](https://i.imgur.com/a9VuOSz.png)

---

## Hierarchy
* /my-department/
  * my-app/
    * dev/
      * db-url
      * db-password
    * prod/
      * db-url
      * db-password
  * other-app/
* /other-department/
* /aws/reference/secretsManager/secret_ID_in_Secrets_Manager
* /aws/service/ami-amzon-linux-latest/amzn2-ami-hvm-x86_64-gp2
