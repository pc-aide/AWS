# CodeBuild Intro

## Acronym
* KMS - Key Management Service
* IAM - Identity & Access Managment
* VPC - Virtual Private Cloud
* SNS - Simple Notification Service

## Doc
* [Test and debug locally with the AWS CodeBuild agent](https://docs.aws.amazon.com/codebuild/latest/userguide/use-codebuild-agent.html)

## Diagram
[<img src="https://i.imgur.com/cN8peqE.png">](https://i.imgur.com/cN8peqE.png)

---

## Intro
* Fully managed buld service
* Alternative to other build tools such as Jenkins
* Continuous scaling (no servers to manage or provision - no build queue)
* Pay for usage: the time it takes to complete the builds
* Leverages Docker under the hood for reproducible builds
* Possibility to extend capabilites leveraging our own base Docker images
* Secure: Integration with KMS for encryption of build artifacts, IAM for build permissions, & VPC for network security, CloudTrail for API calls logging
* Source Code from GitHub/ CodeCommit/ codePipeline/ S3...
* Build instructions can be defined in code (**buildspec.yml** file)
* Output logs to S3 & CloudWatch logs
* Metrics to monitor CodeBuild statistics
* Use CloudWatch Alarms to detect failed builds & trigger notifications
* CloudWatch Events/ Lambda as a Glue
* SNS notifiactions
* Ability to reproduce CodeBuild locally to troubleshoot in case of errors
* **Builds can be defined within CodePipeline or CodeBuild itself**

---

## CodeBuild Support environments
* Java
* Ruby
* Python
* Go
* Node.js
* Android
* .NET Core
* PHP 
* Docker: extend any environment you like

---

## How CodeBuild works
* CodeBuild Container -> passed :
  * S3 Bucket Artifacts
  * Save Logs: CloudWatch S3
    * Running on Build Docker Image
    * Running instructions from buildspec.yml
      * Source Code (CodeCommit)
          * buildspec.yml
      * Build Docker Image (AWS Managed or Custom)
      * S3 Cache Bucket (optional)

### Diagram
[<img src="https://i.imgur.com/426uy1k.png">](https://i.imgur.com/426uy1k.png)

---

## codeBuild BuildSpec
* **buildspec.yml** file must be at the **root* of your code
* Define environment variables:
    * Plantext variables
    * Secure secrets: use SSM Parameter store
* Phases (specify commands to run):
    * Install: install dependencies you may need for your build
    * Pre build: final commands to execute before build 
    * **Build: actual build commands**
    * Post build: finishing touches (zip output for example)
* Artifacts: What to upload to S3 (encrypted with KMS)
* Cache: Files to cache (usually dependencies) to S3 for future build speedup

---

## CodeBuild Local Build
* In case of need of deep troubleshooting beyond logs...
* You can run CodeBuild locally on your desktop (after installing Docker)
* For this, leverage the CodeBuild Agent
