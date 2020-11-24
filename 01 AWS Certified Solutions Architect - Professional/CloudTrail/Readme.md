# CloudTrail

## Acronym
* SDK - Software Developement Kit
* CLI - Command Line Interface
* IAM - Identity & Access Management
* S3 - Siimple Storage Service

## Intro
* Provides governance, compliance & audit for your AWS Account
* CloudTrail is enabled by default
* Get an history of events/API calls made within your AWS Account by:
  * Console
  * SDK
  * CLI
  * AWS Services
* Can put logs from CloudTrail into CloudWatch Logs
* If a resource is deleted in AWS, look into CloudTrail first!
* CloudTrail console shows the **past 90 days** of activity
* The default UI only shows "**Create**", "**Modify**", or "**Delete**" events
* <ins>CloudTrail Trail:</ins>
  * Get a detailed list of all the events you choose
  * Can include events happening at the object level in S3
  * Ability to store these events in S3 for further analysis
  * Can be region specific or be global & include global events (IAM, etc)
  
---

## Solution Architecture: Delivery to S3
