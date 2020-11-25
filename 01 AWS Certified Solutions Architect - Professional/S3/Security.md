# Security

## Doc
* [Bucket Policy Examples](https://docs.aws.amazon.com/AmazonS3/latest/dev/example-bucket-policies.html)

## Acronym
* SSE - Server-Side Encryption
* WORM - Write Once Read Many
* MFA - Multi-Factor Authentication
* VPC - Virtual Private Cloud
* EIP - Elastic IP
* ACL - Access Control List
* IAM - Identity & Access Management
* SDK - Software Developement Kit
* CLI - Command Line Interface
* SNS - Simple Notification Service
* SQS - Simple Queue Service
* SSL - Security Sockets Layer
* KMS - Key Management Service

## S3 Encryption for Objects
* There are 4 methos of encrypting objects in S3
1) **SSE-S3**: encrypts S3 objects using keys handled & managed by AWS
2) **SSE-KMS**: leverage AWS Key Management Service to manage encryption keys
3) **SSE-C**: when you want ot manage your own encryption keys
4) **Client Side Encryption**
* **Gacier**: all data is AES-256 encrypted, key under AWS control

---

## Encryption in transit (SSL)
* AWS S3 exposes:
  * HTTP endpoint: non encrypted
  * HTTPS endpoint: encryption in flight
* You're free to use the endpoint you want, but HTTPS is recommended
* HTTPS is mandatory for SSE-C
* Encryption in flight is also called SSL/TLS

---

## Evnets in S3 Buckets
* S3 Access Logs:
  * Detailed records for the requests that are made to a bucket
  * Might take hours to deliver
  * Might be incomplete (best effort)
* S3 Events Notifications:
  * Receive notifications when certain events happen in your bucket
  * E.g.: new objects created, object removal, restore objects, replication events
  * Destinations: SNS, SQS queue, Lambda
  * Typically delivered in seconds but can take minutes, notification for every object if versioning is enabled, else risk of one notification for two same object write done simultaneously
* Trusted Advisor:
  * Check the bucket permissions (is the bucket public?)
* CloudWatch Events:
  * Need to enable CloudTrail object level logging on S3 first
  * Target can be Lambda, SQS, SNS, etc...
  
---

## Security
* **User based**
  * IAM policies - which API calls should be allowed for a specific user from IAM console
* **Resource Based**
  * Bucket Policies - bucket wide rules from the S3 console - allows cross account
  * Object ACL - finer grain
  * Bucket ACL - less common
  
---

## S3 Bucket Policies
* Use S3 bucket for policy to:
  * Grant public access to the bucket
  * Force objects to be encrypted at upload
  * **Grant access to another account (Cross Account)**
* Optional Conditions on:
  * Public IP or EIP (<ins>not</ins> on Private IP)
  * Source VPC Endpoint - only works with VPC Endpoints
  * CloudFront Origin Identity
  * MFA
  
---

## S3 pre-signed URLs
* Can generate pre-signed URLs using SDK or CLI
  * For downloads (easy, can use the CLI)
  * For uploads (harder, must use the SDK)
* Valid for a default of 3600 seconds, can change timeout with --expires-in [TIME_BY_SECONDS] argument
* Users given a pre-signed URL inherit the permissions of the person who generated the URL for GET/PUT
* Examples:
  * Allow only logged-in users to download a premium video on your S3 bucket
  * Allow an ever changing list of users to download files by generating URLs dynamically
  * Allow temporarily a suser to upload a file to a precise location in our bucket
  
---

## VPC Endpoint Gateway for S3
[<img src="https://i.imgur.com/Jf6ICoF.png">](https://i.imgur.com/Jf6ICoF.png)

---

## S3 Object Lock & Glacier Vault Lock
* S3 Object Lock
  * Adopt a WORM model
  * Block an object version deletion for a specified amount of time
