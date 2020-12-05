# Elastic Beanstalk

## Acronym
* ASG - Auto Scaling Group
* EB - Elastic Beanstalk
* ALB - Application Load Balancer
* ELB - Elastic Load Balancer
* RDS - Relational Database Service
* LB - Load Balancer
* SQS - Simple Queue Service

## Intro
* Elastic Beanstalk is a developer centric view of deploying an application on AWS
* It uses all the component's we've seen before:
  * EC2, ASG, ELBs, RDS, etc...
* But it's all in one view that's easy to make sense of!
* We still have full control over the configuration of each component
* Beanstalk is free but you pay for the underlying instances
* Support for many platforms:
  1) python
  2) Java SE
  3) Node.js
  4) Go
  5) Docker
  6) Java with Tomcat
  7) .NET on Windows Server with IIS
  8) PHP
  9) Ruby
  10) Packer Builder
* If not supported, you can write your custom platform (advanced)
* Beanstalk is great to "**Replatform**" your application from on-premise to the cloud
* Managed service
  * Instance configuration/OS is handled by Beanstalk
  * Deployment strategy is configuration but performed by Elastic Beanstalk
* Just the application code is the responsibility of the developer
* Three architecture models:
  1) Single Instance deployment: good for dev
  2) LB + ASG: great for production or pre-production web applications
  3) ASG only: great for non-web apps in production (**workers environmnet**, etc...)
  
---

## Beanstalk Environments
[<img src="https://i.imgur.com/D8LvTRy.png">](https://i.imgur.com/D8LvTRy.png)

---

## Web Server vs Worker Environment
* If your application performs tasks that are long to complete, offload these tasks to a dedicated **worker environment**
* **Decoupling** your application into two tiers is common
* Example: processing a video, generating a zip file, etc
* You can define periodic tasks in a file **cron.yaml**

### Diagram
[<img src="https://i.imgur.com/8Tcybj9.png">](https://i.imgur.com/8Tcybj9.png)

---

## EB Deployment | Bue/Green
* Not a "direct feature" of EB
* Zero downtime & release facility
* Create a new "stage" environment & deploy v2 there
* The **new environment (green**) can be validated independently & roll back if issues
* Route 53 can be setup using weighted policies to redirect a little bit of traffic to the stage environment
* Using Beanstalk, "swap URLs" (DNS swap) when done with the environment test

### Diagram
[<img src="https://i.imgur.com/JJGDyvM.png">](https://i.imgur.com/JJGDyvM.png)
