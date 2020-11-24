# KMS

## Acronym
* KMS - Key Management Service
* IAM - Identity & Access Management
* SDK - Software Developement Kit
* CLI - Command Line Interface
* EBS - Elastic Block Store
* S3 - Simple Storage Service
* RDS - Relational Database Service
* SSM - System Manager
* CMK - Customer Master Key

## Intro
* Anytime your hear "encryption" for an AWS service, it's most likely KMS
* Easy way to control access to your data, AWS manages keys for us
* Fully integrated with IAM for authorization
* Seamlessly integrated into:
  * EBS: encrypt volumes
  * S3: Server side encryption of object
  * Redshift: encryption of data
  * RDS: encryption of data
  * SSM: Parameter store
  * Etc ...
* But you can also use the CLI/SDK

---

## KMS 101
* The value in KMS is that the CMK used to encrypt data can never be retrieved by the user, & the CMK can be rotated for extra security
* Never ever store your secrets in plaintext, espicially in your code!
* Encrypted secrets can be stored in the code/environment variables
* KMS can only help in **encrypting up to 4KB of data** per call
* **If data > 4KB**, use **Envelope Encryption**
  * by generating a **data key** & using the data key that you control to encrypt the data
* To give access to KMS to someone:
  * Make sure the Key Policy allows the user
  * Make sure the IAM Policy allows the API calls
* **Track API calls made to KMS in CloudTrail**

---

## Types of KMS Keys
1) Customer Manager CMK:
  * Create, manage & use, can enable or disable
  * Possibility of rotation policy (new key generated every year, old key preserved)
  * Can add a key policy (resource policy)
  * Leverage for envelope encryption
2) AWS managed CMK:
  * Used by AWS service (aws/s3, aws/ebs, aws/redshift)
  * Managed by AWS
  
### Img
[<img src="https://i.imgur.com/gTMrfFK.png">](https://i.imgur.com/gTMrfFK.png)

---

## How does KMS work? | API - Encrypt & Decrypt
[<img src="https://i.imgur.com/5pmOXMf.png">](https://i.imgur.com/5pmOXMf.png)
