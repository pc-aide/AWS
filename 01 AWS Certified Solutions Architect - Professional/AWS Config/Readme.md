# AWS Config

## Acronym
* SG - Security Group
* ALB - Application Load Balancer
* EBS - Elastic Block Storage
* SNS - Simple Notification Service
* SSM - System Manager
* gp2- general purpose v2

## Intro
* Helps with auditing & recording  **compliance** of your AWS resources
* Helps record configurations & changes over time
* AWS config Rules does not prevent actions from happening (no deny)
* Questions that can be solved by AWS Config:
  * Is there unrestricted SSH access to my SGs
  * Do my buckets have any public access?
  * How has my ALB configuration changed over time?
* You can **receive alerts (SNS) for any changes**
* AWS Config is a per-region service
* Can be aggregated across regions & accounts

---

## Resource
* View compliance of a resource over time:

[<img src="https://i.imgur.com/1qU4DNx.png">](https://i.imgur.com/1qU4DNx.png)

* View configuration of a resource over time:

[<img src="https://i.imgur.com/5sdfTPx.png">](https://i.imgur.com/5sdfTPx.png)

* View CloudTrail API calls if enabled

## Rules
* Can use AWS managed config rules (over 75)
* Can make custom config rules (must be defined in Lambda)
  * Evaluate if each EBS disk is of type gp2
  * Evaluate if each EC2 instance is t2.micro
* Rules can be evaluated/triggered:
  * For each config change
  * And / or: at regular time intervals
  * Can trigger CloudWatch Events if the rule is non-compliant (& chain with Lambda)
* Rules can have autom remediations:
  * If a resource is not compliant, you can trigger an auto remediation
  * Define the remediation through **SSM Automations**
  * Ex: remediate SG rules, stop instance with non-approved tags
