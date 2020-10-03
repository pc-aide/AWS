# Beanstalk Advanced Concepts

## Doc
* [https-redirect](https://github.com/awsdocs/elastic-beanstalk-samples/tree/main/configuration-files/aws-provided/security-configuration/https-redirect)

## Acronym
* EB - Elastic Beanstalk
* LB - Load Balancer
* Cfg - Configuration
* ALB - Application Load Balancer
* ACM - Amazon Certificate Manager
* SG - Security Group
* SQS - Simple Queue Service
* OS - Operating System
* AMI - Amazon Machine Image

## EB & HTTPS
* Beanstalk with HTTPS
    * Idea: Load the SSL certificate onto the LB
    * Can be done from the Console (EB console, LB cfg)
    * Can be done from the code: .ebextensions/securelistener-alb.config
    * SSL Certificate can be provisoned using ACM or CLI
    * Must configure a SG rule to allow incoming port 443 (HTTPS port)
* Beanstalk redirect HTTP to HTTPS
    * Configure your instans to redirect HTTP to HTTPS - check the Doc
    * OR configure the ALB only with a rule
    * Make sure health checks are not redirected (so they  keep giving 200 OK)
    
---

## Web Server vs Worker Envrionment
* If your application performs tasks that are long to complete, offload these tasks to a dedicated **worker environment**
* **Decoupling** your application into two tiers is common
* Example: processing a video, generating a zip file, etc
* You can define periodic tasks in a file **cron.yaml**

### Diagram
[<img src="https://i.imgur.com/sEsPlDL.png">](https://i.imgur.com/sEsPlDL.png)

---

## EB - Custom Platform (Advanced)
* Custom Platforms are very advanced, they allow to define from scratch:
    * The OS
    * Additional Software
    * Scripts that Beanstalk runs on these platforms
* <ins>Use case:</ins> app laguage is incompatible with Beanstalk & doesn't use Docker
* To create your own platform:
    * Define an AMI using **Platform.yaml** file
    * Build that platform using the **Packer software** (open source tool to create AMIs)
* Custom Platform vs Custom Image (AMI):
    * Custom Image is to tweak an <ins>existing</ins> Beanstalk Platform (Python, Node.js, Java...)
    * Custom Platform is to create <ins>an entirely new</ins> Beanstalk Platform
