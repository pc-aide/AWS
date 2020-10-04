# CodeDeploy Intro

## Acronym
* EB - Elastic Beanstalk
* IAM - Identity & Access Management
* ASG - Auto-Scaling Group

## Doc

## Intro
* We want to deploy our application automatically to many EC2 instances
    * Example: 100 EC2 to deploy & you manage this instances
* These instances are not managed by EB
* There are several ways to handle deployments using open source tools:
    * Ansible
    * Terraform
    * Chef
    * Puppet
    * etc
* We can use the managed Service AWS CodeDeploy
    
### Diagram
[<img src="https://i.imgur.com/lQAYI9E.png">](https://i.imgur.com/lQAYI9E.png)

---

## CodDeploy - Steps to make it work
* Each EC2 Machine (or On Premise machine) must be running the **CodeDeploy Agent** (software)
* The agent is continuously polling AWS CodeDeploy for work to do
* CodeDeploy sends **appsepec.yml** file
* Application is pulled from GitHub or S3
* EC2 Will run the deployment instructions
* CodeDeploy Agent will report of success / failure of deployment on the instance

### Diagram
[<img src="https://i.imgur.com/o7NCj2J.png">](https://i.imgur.com/o7NCj2J.png)

---

## CodeDeploy - Other
* EC2 instances are grouped by deployment group (dev/ test/ prod)
* Lots of flexibility to define any kind of deployments
* CodeDeploy can be chained into CodePipeline & use artifacts from there
* CodeDeploy can re-use existing setup tools, works with any application, auto scaling integration
* Note: Blue / Green only works with EC2 instances (not on premise)
* Support for Lambda deployments 
* CodeDeploy does not provision resources
    * It assumes that your EC2 instances are already existing
    
---

## CodeDeploy Primary Components
* **Application**: unique name
* **Compute platform**: EC2/On-Premise or Lambda
* **Deployment configuration**: Deployment rules for success/ failures
    * EC2/ On-Premise: you can specify the minimum number of healthy instances for the deployment
    * Lambda: specify how traffic is routed to your updated Lambda function versions
* **Deployment group**: group of tagged instances (allows to deploy gradually)
* **Deployment type**: In-place deployment or Blue/ green deployment
* **IAM instances profile**: need to give EC2 the permissions to pull from S3/ GitHub
* **Application Revision**: application code + appspec.yml file
* **Service role: Role for CodeDeploy to perform what it needs
* **Target revision**: Target deployment application version

---

## CodeDeploy AppSpec
* File section: how to source & copy from S3 / GitHub to filesystem
* Hooks: set of instructions to do to deploy the new version (hooks can have timeouts). The order is:
    * ApplicationStop
    * DownloadBundle
    * BeforeInstall
    * AfterInstall
    * ApplicationStart
    * **ValidateService: really important**
    
---

## codeDeploy Deploy & Hooks Order
| Event              | Start time                   | End time                     | Duration             | Status    |
| ------------------ | ---------------------------- | ---------------------------- | -------------------- | --------- |
| ApplicationStop    | sept 26, 2018 7:51:29 AM UTC | sept 26, 2018 7:51:29 AM UTC | less than one second | Succeeded |
| DownloadBundle     | sept 26, 2018 7:51:30 AM UTC | sept 26, 2018 7:51:30 AM UTC | less than one second | Succeeded |
| BeforeInstall      | sept 26, 2018 7:51:31 AM UTC | sept 26, 2018 7:51:32 AM UTC | 2 secs               | Succeeded |
| Install            | sept 26, 2018 7:51:33 AM UTC | sept 26, 2018 7:51:33 AM UTC | less than one second | Succeeded |
| AfterInstall       | sept 26, 2018 7:51:34 AM UTC | sept 26, 2018 7:51:34 AM UTC | less than one second | Succeeded |
| ApplicationStart   | sept 26, 2018 7:51:35 AM UTC | sept 26, 2018 7:51:35 AM UTC | less than one second | Succeeded |
| ValidateService    | sept 26, 2018 7:51:36 AM UTC | sept 26, 2018 7:51:36 AM UTC | less than one second | Succeeded |
| BeforeAllowTraffic | sept 26, 2018 7:51:49 AM UTC | sept 26, 2018 7:51:49 AM UTC | less than one second | Succeeded |
| AllowTraffic       | sept 26, 2018 7:51:50 AM UTC | sept 26, 2018 7:52:11 AM UTC | 21 secs              | Succeeded |
| AfterAllowTraffic  | sept 26, 2018 7:52:12 AM UTC | sept 26, 2018 7:52:12 AM UTC | less than one second | Succeeded |

---

## CodeDeploy Deployment Config
* Configs:
    * One a time: one instance at a time, one instance fails => deployment stops
    * Half at a time: 50%
    * All at once: quick but no healthy host, downtime. Good for dev
    * Custom: min healthy host = 75%
* Failures:
    * Instances stay in "failed state"
    * New deployments will first be deployed to "failed state" instances
    * To rollback: redeploy old deployment or enable automated rollback for failures
* Deployment Targets:
    * Set of EC2 instances with tags
    * Directly to an ASG
    * Mix of ASG/ Tags so you can build deployment segments
    * Customization in scripts with DEPLOYMENT_GROUP_NAME environment variables
    
---

## In Place Deployment - Half at a time
[<img src="https://i.imgur.com/Mrggr87.png">](https://i.imgur.com/Mrggr87.png)

---

## Blue Green Deployment
[<img src="https://i.imgur.com/B1gweG4.png">](https://i.imgur.com/B1gweG4.png)
