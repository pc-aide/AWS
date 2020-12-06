# SSM

## Acronym
* AMI - Amazon Machine Image
* CW - CloudWatch
* IAM - Identity & Access Management
* SSM - Systems Manager

## Intro
* Heps you manage your **EC2 & On-Premise** systems at scale
* Get operational insights about the stae of your infrastructure
* Easily detect problems
* **Patching automation for enhanced compliance**
* Works for both Windows & Linus OS
* Integrated with CW metrics/dashboards
* Integrate with AWS Config
* **Free service**

---

## Features
* Resource Groups
* Insights:
  * Insights Dashboard
  * Inventory: discover & audit the software installed
  * Compliance
* **Parameter Store**
  * Store your credentials
* Action:
  * Automation (shut down EC2, create AMIs)
  * **Run Command**
  * Session Manager
  * **Patch Manager**
  * **Maintenance Windows**
  * State Manager: define & amintaining configuration of OS & applications
  
---

## How Systems Manager works
* We need to install the SSM agent onto the systems we control
* Installed by default on Amazon Linux AMI & some Ubuntu AMI
* If an instance can't be controlled with SSM, it's probably an issue with the SSM agent!
* Make sure the EC2 instances have a proper IAM role to allow SSM actions

### Diagram
[<img src="https://i.imgur.com/Vd0WIol.png">](https://i.imgur.com/Vd0WIol.png)

---

## Run Command
* Execute a document (= script) or just run a command
* Run command across multiple instances (using resource groups)
* Rate Control/Error Control
* Integrated with IAM & CloudTrail
* **No need for SSH**
* Results in the console
