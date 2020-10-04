# CodePipeline Overview

## Acronym
* ECS - Elastic Container Service
* CI/CD - Continuous Integration / Continuous Delivery
* SNS - Simple Notification Service
* IAM - Identity & Access Management

## Doc

## Intro
* Continuous delivery
* Visual workflow
* Source: GitHub/CodeCommit/S3 
* Build: CodeBuild/Jenkins/etc
* Load Testing: 3<sup>rd</sup> party tools
* Deploy: AWS codeDeploy/Beanstalk/CloudFormation/ECS
* Made of stages:
    * Each stage can have sequential actions & / or parallel actions
    * Stages examples: build/ Test/ Deploy/ Load Test/ etc
    * Manual approval can be defined at any stage
    
---

## Technology Stack for CI/CD
[<img src="https://i.imgur.com/KzF8EqO.png">](https://i.imgur.com/KzF8EqO.png)

---

## AWS CodePipeline Artifacts
* Each pipeline stage can create "artifacts"
* Artifacts are passed stored in S3 & passed on to the next stage

### Diagram
[<img src="https://i.imgur.com/BE7MVnN.png">](https://i.imgur.com/BE7MVnN.png)

---

## CodePipeline Troubleshooting
* CodePipeline state changes happen in **CloudWatch Events**, which can in return create SNS notifications
    * Ex: you can create events for failed pipelines
    * Ex: you can create events for cancelled stages
* If CodePipeline fails a stage, your pipeline stops & you can get information in the console
* CloudTrail can be used to audit AWS API calls
* If Pipeline can't perform an action, make sure the "IAM Service Role" attached does have enough permissions (IAM Policy)
