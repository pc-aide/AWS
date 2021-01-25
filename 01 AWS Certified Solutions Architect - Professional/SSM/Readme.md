# SSM

## Doc
* [Patching your Windows EC2 instances using AWS Systems Manager Patch Manager](https://aws.amazon.com/blogs/mt/patching-your-windows-ec2-instances-using-aws-systems-manager-patch-manager/)

## Acronym
* AMI - Amazon Machine Image
* CW - CloudWatch
* IAM - Identity & Access Management
* KMS - Key Management Service
* SSM - Systems Manager

## Intro
* Systems Manager allows you to view & control your infrastructure in an automated fashion
* Both EC2 & On-Premises servers can be made into managed instances
* Parameter Store is available to provide a secure, hierarchical storage for secrets
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

### Diagram
[<img src="https://i.imgur.com/rNrbQcb.png">](https://i.imgur.com/rNrbQcb.png)

---

## SSM Path Manager - Predefined Path Baselines
* Defines which patches should or shouldn't be installed on your instances
* <ins>Linux:</ins>
  * AWS-AmazonLinux2DefaultPatchBaseline
  * AWS-CentOSDefaultPatchBaseline
  * AWS-RedHatDefaultPatchBaseline
  * AWS-SuseDefaultPathcBaseline
  * AWS-UbuntuDefaultPatchBaseline   
* <ins>Windows:</ins> (patches are auto-approved 7 days after the release)
  * **AWS-DefaultPatchBaseline**: install OS patch CriticalUpdates & SecurityUpdates
  * AWS-WindowsPredefinedPatchBaseline-OS: same as "AWS-DefaultPatchBaseline"
  * AWS-WindowsPredefinedPatchBaseline-OS-Applications: also updates Microsoft applications
* Can define your own custom patch baselines as well (OS, classification, severity...)

---

## SSM Patch Managers - Steps
1) Define a **path baseline** to use (or multiple if you have multiple environments)
2) Define path groups: define based on tags, example different environments (dev,test,prod) - use tag **Patch Group**
3) Define **Maintenance Windows** (schedule, duration, registered targets/patch groups & registered tasks)
4) Add the **AWS-RunPatchBaseline Run Command** as part of the registered tasks of the Maintenance Windows (works cross platform Linux & Windows)
5) Define **Rate Control** (concurrency & error threshold) for the task
6) Monitor **Path Compliance** using **SSM Inventory**

### Diagram
[<img src="https://i.imgur.com/XldGkQ4.png">](https://i.imgur.com/XldGkQ4.png)

---

## Parameter Store
* Secure storage for configuration & secrets
* Optional Seamless Encryption using KMS
* Serverless, scalable, durable, easy SDK, free
* Version tracking of configurations/secrets
* Configuration management using path & IAM
* Notifications with CW Events
* Integration with CloudFormation
* Can retrieve secrets from Secrets Manager using the SSM Parameter Store API

### Diagram
[<img src="https://i.imgur.com/irrNqyD.png">](https://i.imgur.com/irrNqyD.png)

---

## Parameter Store Hierarchy
* /my-department/
  * my-app/
    * dev/
      * db-url
      * db-password
    * prod/
      * db-url
      * db-password
  * other-app/
* /other-department/
* /aws/reference/secretsmanager/secret_ID_in_Secrets_Manager
* /aws/service/ami-amazon-linux-latest/amzn2-ami-hvm-x86_64-gp2

## Diagram if use Lambda
[<img src="https://i.imgur.com/tHKWy9g.png">](https://i.imgur.com/tHKWy9g.png)
