# CodeCommit Overview

## Acronym
* HA - High Available
* CI - Continuous Integration
* IAM - Identity & Access Management
* MFA - Multi-Factor Authentication
* KMS - Key Management Service
* SNS - Simple Notification Service

## Doc

## Intro
* **Version control** is the ability to understand the various changes that happened to the code over time (& possibly roll back)
* All these are  enabled by using a version control system such as **Git**
* A Git repository can live on on's machine, but usually lives on a central online repository
* Benefits are:
    * Collaborate with other developers
    * Make sure the ocde is backed-up somewhere
    * Make sure it's fully viewable & auditable
    
---

## CodeCommit
* Git repositories can be expensive 
* The industry includes:
    * GitHub: free public repositories, paid private ones
    * BitBucket
    * Etc
* & AWS CodeCommit
    * private Git repositories
    * No size limit on repositories (scale seamlessly)
    * Fully managed, HA
    * Code only in AWS Cloud account => increased security & compliance
    * Secure (encrypted, access control, etc)
    * Integrated with Kenkins/CodeBuild/other CI tools

### Diagram
[<img src="https://i.imgur.com/qcbrGDS.png">](https://i.imgur.com/qcbrGDS.png)

---

## CodeCommit Security
* Interactions are done using Git (standard)
* Authentication in Git:
      * SSH Keys: AWS users can configure SSH Keys in their IAM Console
      * HTTPS: Done through the AWS CLI Authentication helper or Generating HTTPS credentials
      * MFA can be neabled for extra safety
* Authorization in Git:
      * IAM Policies manage user/roles rights to repositories
* Encryption:
      * Repositories are automatically encrypted at rest using KMS
      * Encrypted in transit (can only use HTTPS or SSH - both secure)
* Cross Account access:
      * Don't share your SSH keys
      * Don't share your AWS credentials
      * Use IAM Role in your AWS Account & use **AWS STS** (with AssumeRole API)
         * it's basically a cross-account access API call
         
---

## CodeCommit vs GitHub
* Similarities:
      * Both are git repositories
      * Both support code review (pull requests)
      * GitHub & CodeCommit can be intregrated with AWS CodeBuild
      * Both support HTTPS & SSH method of authentication
* **Differences**:
      * Security:
         * GitHub: GitHub Users   
         * CodeCommit: AWS IAM users & roles
      * Hosted:
         * GitHub: hsoted by GitHub
         * GitHub Enterprise: self hosted on your servers
         * CodeCommit: managed & hosted by AWS
      * Hosted:
         * GitHub UI is fully featured
         * CodeCommit UI is minimal
         
---

## CodeCommit Notifications
* you can trigger notifications in CodeCommit using:
      * **AWS SNS**
      * or
      * **Lambda**
      * or
      * **CloudWatch Event Rules**
* Use case for notification SNS/Lambda notifications:
      * Deletion of branches
      * Trigger for pushes that happens in master branch
      * Notify external Build System
      * Trigger **Lambda** function to perform condebase analysis (maybe credentials got commited in the code?)
* Use cases for CloudWatch Event Rules:
      * Trigger for pull request updates (created/updated/deleted/commented)
      * Commit comment events
      * CloudWatch Event Rules goes into an SNS topic
