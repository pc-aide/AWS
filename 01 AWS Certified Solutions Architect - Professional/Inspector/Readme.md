# Inpector

## Acronym
* AMI - Amazon Machine Image
* SNS - Simple Notification Service

## Intro
* For this moment, not available for ca-central-1 (27-10-2020)
* Only for EC2 instances (started from an AMI)
* **Analyze** the running OS against known **vulnerabilities**
* Analyze against unintended network accessibility
* **Inpector Agen** must be installed on OS in EC2 instances
* Define template (rules package, duration, attibutes, SNS topics)
* No own custom rules possible - only use AWS managed rules
* After the assessment, you get a report with a list of vulnerabilities
