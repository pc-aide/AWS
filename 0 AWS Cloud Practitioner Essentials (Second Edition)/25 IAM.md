# IAM

## Terminology
* CloudTrail

## Acronym
* IAM - Identity & Access Management
* API - Application Program Interface
  * S3 is an API
* S3 - Simple Storage Service

## Model
* User
  * Permanent (could be human or machine)
* Group
  * Collection group users
* Role
  * Temp
* Policy Docs (we can detach this object if hacked by user + pwd)
  * WhiteList
  * BlackList
  * Certain conditions
  * Scheduled (e.g. Monday)
  * E.g.
    * Deny EC2.production to stop
    * root (MFA)
    
[<img src="https://i.imgur.com/0J2gRnc.png">](https://i.imgur.com/0J2gRnc.png)
