# OpsWorks

## Acronym
* ALB - Application Load Balancer
* RDS - Relational Database Service
* SSM - System Manager
* ntp - network time protocol

## Intro
* Chef & Puppet help you perform server configuration automatically, or repetitive actions
* They work great with EC2 & On-Premise VM
* AWS OpsWorks = Managed Chef & Puppet
* It's an alternative to SSM
* **If you're already using cookbooks (chef) on-premise, OpsWorks is good**
* **Migrating from other tech to OpsWorks or vice-verse is not easy**

---

## Quick word on Chef/Puppet
* They help with managing configuration as code
* Helps in having consistent deployments
* Works with Linux/Windows
* Can automate: user accounts, cron, ntp, packages, services...
* They leverage "Recipes", "Cookbooks" or "Manifests"
* Chef/Puppet have simularities with SSM/Beanstalk/CloudFormation but they're open-source tools that work cross-cloud

---

## OpsWorks Architecture
[<img src="https://i.imgur.com/OSssdS1.png">](https://i.imgur.com/OSssdS1.png)
