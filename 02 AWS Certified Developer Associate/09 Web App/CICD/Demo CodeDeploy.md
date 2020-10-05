# Demo CodeDeploy

## Acronym
* IAM - Identity & Access Management
* SG: Security Group
* LB - Load Balancer

## Doc

## Intro
* First need to create an IAM role
  * We need 2x Roles:
    * Type of trusted entitty: CodeDeploy
    * Select your use case: CodeDeploy
    
[<img src="https://i.imgur.com/QUjEOku.png">](https://i.imgur.com/QUjEOku.png)

* Next\Review
    * Role name: CodeDeployServiceRole
* Create role

* Second Role
    * Type of trusted entity: EC2
        * we'll create EC2 instance & be running the CodeDeploy agent (software)
* Attach permission policies
    * Filter policies : s3 (pull acces)
    * CheckBox: AmazonS3ReadOnlyAccess
    
[<img src="https://i.imgur.com/EOXCImM.png">](https://i.imgur.com/EOXCImM.png)

* Review\Role name: EC2InstanceRoleForCodeDeploy
* Create role

* CodeDeploy\Getting started\Create application
    * Applicatin name: Demo-Application
    * Compute platform: EC2/On-premise
    
[<img src="https://i.imgur.com/NROHpzQ.png">](https://i.imgur.com/NROHpzQ.png)

* Before to Create deployment group
* We need EC2 instance
* Launch instance:
  * AMI : Amzon Linux 2 
  * IAM Role: EC2InstanceRoleForCodeDeploy
  * SG: SSH + HTTP
  
* SSH (EC2):
* Need to install CodeDeploy agent :
* command.sh
````shell
#!/bin/bash

# Installing CodeDeploy Agent
sudo yum update -y
sudo yum install -y ruby

# Dowload the agent 
wget https://aws-codedeploy-ca-central-1.s3.ca-central-1.amazonaws.com/latest/install

# Add executable
chmod +x ./install
sudo ./install auto

# Check status
sudo service codedeploy-agent status
````
[<img src="https://i.imgur.com/x6kaed9.png">](https://i.imgur.com/x6kaed9.png)

* add tag EC2
    * Key: Environment
    * value: Dev

* Back to CodeDeploy\Application
* Create deployment group
    * Deployment group name: Development-Instances
    * service role: CodeDeployServiceRole
    * Deployment type: In-place
    * Environment cfg
        * Amazon EC2 instances
        * key: Environment
        * Value: Dev  
            * Note: all instances with this environment cfg (tag: key & value), will be part of this deployment group
    * Deployment settings
        * CodeDeployDefault.AllAtOnce
    * LB: disabled
* Create deployment group

[<img src="https://i.imgur.com/uqJISTj.png">](https://i.imgur.com/uqJISTj.png)
[<img src="https://i.imgur.com/SMxtPps.png">](https://i.imgur.com/SMxtPps.png)
[<img src="https://i.imgur.com/RGhDTow.png">](https://i.imgur.com/RGhDTow.png)
[<img src="https://i.imgur.com/Xuka1gZ.png">](https://i.imgur.com/Xuka1gZ.png)

* CodeDeploy\application
* Create deployment

[<img src="https://i.imgur.com/uppxPYm.png">](https://i.imgur.com/uppxPYm.png)

* S3\Create bucket: demo-01-codedeploy
* upload SampleApp_Linux
* file **appspec.yml*
````yml
version: 0.0
os: linux
files:
  - source: /index.html
    destination: /var/www/html/
hooks:
  BeforeInstall:
    - location: scripts/install_dependencies
      timeout: 300
      runas: root
    - location: scripts/start_server
      timeout: 300
      runas: root
  ApplicationStop:
    - location: scripts/stop_server
      timeout: 300
      runas: root
````

* upload the zip file to S3
* copy path

[<img src="https://i.imgur.com/bPiFIP5.png">](https://i.imgur.com/bPiFIP5.png)
[<img src="https://i.imgur.com/Tn2kH7a.png">](https://i.imgur.com/Tn2kH7a.png)
[<img src="https://i.imgur.com/kRFzIiV.png">](https://i.imgur.com/kRFzIiV.png)
[<img src="https://i.imgur.com/0LyRF5O.png">](https://i.imgur.com/0LyRF5O.png)
[<img src="https://i.imgur.com/Z5bQSyI.png">](https://i.imgur.com/Z5bQSyI.png)
[<img src="https://i.imgur.com/7g8FY7L.png">](https://i.imgur.com/7g8FY7L.png)
[<img src="https://i.imgur.com/IXDAEVd.png">](https://i.imgur.com/IXDAEVd.png)

* Deployment group: Deployment-Instances
* Revison location: copy path S3
* Create deployment

[<img src="https://i.imgur.com/BYuZKBm.png">](https://i.imgur.com/BYuZKBm.png)
[<img src="https://i.imgur.com/6z8dG6x.png">](https://i.imgur.com/6z8dG6x.png)
[<img src="https://i.imgur.com/OtZHltE.png">](https://i.imgur.com/OtZHltE.png)

* Deployment status: Succeeded:

[<img src="https://i.imgur.com/DrSSGEH.png">](https://i.imgur.com/DrSSGEH.png)

* View events:

[<img src="https://i.imgur.com/GEPmQUQ.png">](https://i.imgur.com/GEPmQUQ.png)

* Deployment details:

[<img src="https://i.imgur.com/AGXVGz6.png">](https://i.imgur.com/AGXVGz6.png)

* Browser:

[<img src="https://i.imgur.com/uX8Htw6.png">](https://i.imgur.com/uX8Htw6.png)

* Deployment configurations:

[<img src="https://i.imgur.com/jAGkXla.png">](https://i.imgur.com/jAGkXla.png)

* On-premises instances:

[<img src="https://i.imgur.com/aZKMRdA.png">](https://i.imgur.com/aZKMRdA.png)
