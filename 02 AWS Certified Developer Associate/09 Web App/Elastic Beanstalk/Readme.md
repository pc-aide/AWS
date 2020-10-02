# Elastic Beanstalk

## Acronym
* DB - database
* LB - Load Balancer
* ALB - Application Load Balancer
* ASG - Auto-Scaling Group
* ELB - Elastic Load Balancer
* RDS - Relational database service

## Doc

## Topology
* Typical architecture: Web App 3tier
    * 1-tier: public
    * 2-tier: private
    * 3-tier: data
    
[<img src="https://i.imgur.com/ddzqRs0.png">](https://i.imgur.com/ddzqRs0.png) 

---

## Developer problems on AWS
* Managing infrastructure
* Deploying Code
* Configuring all the DBs, LBs, etc
* Scaling concerns
* Most web apps have the same architecture (ALB + ASG)
* All the developers want is for their **code to run**!
* Possibly, consistently across different applications & environments

---

## Elastic Beanstalk Overview
* Elastic Beanstalk is a developer centric view of deploying an application on AWS
* It uses all the component's we've seen before:
    * EC2, ASG, ELB, RDS, etc
* But it's all in onve view that's easy to make sense of!
* We still have full control over the configuration
* Beanstalk is free but you pay for the underlying instances

---

## Elastic Beanstalk
* Managed service
    * Instance configuration / OS is handled by Beanstalk
    * Deployment strategy is configurable but performed by Elastic Beanstalk
* Just the application code is the responsibility of the developer
* Three architecture models:
    1) Single Instance deployment: good for dev
    2) LB + ASG: great for production or pre-production web applications
    3) ASG only: great for no-web apps in production (workers, etc)
      * some message on queue
* Elastic Beanstalk has three components
    1) Application (your code)
    2) Application version: each deployment gets assigned a version
    3) Envrionment name (dev, test, prod...): free naming
* You deploy application versions to environments & can promote application versions to the next environment
* Rollback feature to previous application version
* Full control over lifecycle of environments  
* Support for many platforms:
    * Go
    * Java SE
    * Java with Tomcat
    * .NET on Windows Server with IIS
    * Node.js
    * PHP
    * Python
    * Ruby
    * Packer Builder
    * Single Container Docker
    * Multicontainer Docker
    * Preconfigured Docker
    * **If not supported, you can write your custom platform (advanced)

### Diagram
[<img src="https://i.imgur.com/tCyk1xP.png">](https://i.imgur.com/tCyk1xP.png)
