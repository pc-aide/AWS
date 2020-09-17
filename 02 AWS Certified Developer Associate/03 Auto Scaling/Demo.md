# Demo

## Doc
* [Launch templates](https://docs.aws.amazon.com/autoscaling/ec2/userguide/LaunchTemplates.html?icmpid=docs_ec2as_help_panel)
* [Launch configurations](https://docs.aws.amazon.com/autoscaling/ec2/userguide/LaunchConfiguration.html?icmpid=docs_ec2as_help_panel)
* [Launching an instance from a launch template](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-launch-templates.html?icmpid=docs_ec2_console)
* [Auto Scaling groups with multiple instance types and purchase options](https://docs.aws.amazon.com/autoscaling/ec2/userguide/asg-purchase-options.html?icmpid=docs_ec2as_help_panel)
* [Launching Auto Scaling instances in a VPC](https://docs.aws.amazon.com/autoscaling/ec2/userguide/asg-in-vpc.html?icmpid=docs_ec2as_help_panel)
* [Health checks for Auto Scaling instances](https://docs.aws.amazon.com/autoscaling/ec2/userguide/healthcheck.html?icmpid=docs_ec2as_help_panel)
* [Adding Elastic Load Balancing health checks to an Auto Scaling group](https://docs.aws.amazon.com/autoscaling/ec2/userguide/as-add-elb-healthcheck.html?icmpid=docs_ec2as_help_panel)
* [Setting capacity limits for your Auto Scaling group](https://docs.aws.amazon.com/autoscaling/ec2/userguide/asg-capacity-limits.html?icmpid=docs_ec2as_help_panel)
* [Maintaining a fixed number of instances in your Auto Scaling group](https://docs.aws.amazon.com/autoscaling/ec2/userguide/as-maintain-instance-levels.html?icmpid=docs_ec2as_help_panel)
* [Target tracking scaling policies for Amazon EC2 Auto Scaling](https://docs.aws.amazon.com/autoscaling/ec2/userguide/as-scaling-target-tracking.html?icmpid=docs_ec2as_help_panel)
* [Getting Amazon SNS notifications when your Auto Scaling group scales](https://docs.aws.amazon.com/autoscaling/ec2/userguide/ASGettingNotifications.html?icmpid=docs_ec2as_help_panel)

## Acronym
* AZ - Availability Zone
* SG - Security group
* LB - Load Balancer
* ELB - Elastic Load Balancing
* ALB - Application Load Balancer
* TG - Target Group

## MySetup
* us-east with 3x instances on AZ differents

### EC2
[<img src="https://i.imgur.com/o7nO9wx.png">](https://i.imgur.com/o7nO9wx.png)

* Same SG for the instances:

[<img src="https://i.imgur.com/e5b9LuP.png">](https://i.imgur.com/e5b9LuP.png)

* ALB cfg:
    * AZ: 3 times
    * SG: LB-HTTP-IN-Any
    * TG (listener) - **empty** - it's ASG will take this stepp..
    * Browser: 503
    
[<img src="https://i.imgur.com/hXuDE3m.png">](https://i.imgur.com/hXuDE3m.png)
[<img src="https://i.imgur.com/o86mhZX.png">](https://i.imgur.com/o86mhZX.png)
[<img src="https://i.imgur.com/cHW2X33.png">](https://i.imgur.com/cHW2X33.png)
[<img src="https://i.imgur.com/ADAXEzP.png">](https://i.imgur.com/ADAXEzP.png)
[<img src="https://i.imgur.com/S1toodM.png">](https://i.imgur.com/S1toodM.png)

## Create Auto Scaling group
* Name: SimpleAppTestASG
* Create a lunch template

[<img src="https://i.imgur.com/1bC9Hlq.png">](https://i.imgur.com/1bC9Hlq.png)

### Create launch template
* Name: SimpleAppTestTemplate
* Description: SimpleAppTestTemplate

[<img src="https://i.imgur.com/cxVZqu6.png">](https://i.imgur.com/cxVZqu6.png)

* AMI: ami-0c94855ba95c71c99
* Instance Type: t2.micro
* key pair: EC2Ama-US
* Networking platform: Default (VPC)
* SG: SSH-IN-MyIP, HTTP-LB-IN
* Advanced Details
   * User data:
````bash
#!/bin/bash

###############################################
### USE THIS FILE IF LANCHED AMAZON LINUX 2 ###
###############################################

# Priviledges
sudo su

# TimeZone
timedatectl set-timezone America/Toronto

# Install httpd
yum update -y
yum install -y httpd
systemctl start httpd
systemctl enable httpd
echo "Hello World from $(hostname -f)" > /var/www/html/index.html
````
* Create Launch template
* Go back to "New ASG"

[<img src="https://i.imgur.com/ZSvTp1D.png">](https://i.imgur.com/ZSvTp1D.png)

* Next
   * Purchase options..: default (Adhere to launch...)
   * Subnets: my 3x subnets (1a,1b,1d)
   
[<img src="https://i.imgur.com/IkyelMv.png">](https://i.imgur.com/IkyelMv.png)

* Next
* LB:
   * Checkbox: Enable LB
   * Checkbox: ELB
   
[<img src="https://i.imgur.com/UCNlVO9.png">](https://i.imgur.com/UCNlVO9.png)

* Next
* Size:
   * Desired capacity: 1
   * Minimum capacity: 1
   * Maximum capacity: 3 
   
[<img src="https://i.imgur.com/3MFmX5s.png">](https://i.imgur.com/3MFmX5s.png)

* Scaling policies: default (none)
* Next
* Next twice  (Add notifications, Add tags)
* create Auto Scaling group

[<img src="https://i.imgur.com/sqwUXwE.png">](https://i.imgur.com/sqwUXwE.png)
* Create new instance:

[<img src="https://i.imgur.com/sEH2pAI.png">](https://i.imgur.com/sEH2pAI.png)
* it's new instance attached to TG for my ALB:

[<img src="https://i.imgur.com/JWgdwhK.png">](https://i.imgur.com/JWgdwhK.png)
[<img src="https://i.imgur.com/XZRQEyb.png">](https://i.imgur.com/XZRQEyb.png)
[<img src="https://i.imgur.com/ce0pPI2.png">](https://i.imgur.com/ce0pPI2.png)
[<img src="https://i.imgur.com/YVSbpBa.png">](https://i.imgur.com/YVSbpBa.png0)
[<img src="https://i.imgur.com/cGMbuv1.png">](https://i.imgur.com/cGMbuv1.png)

* One instance & CPU low:

[<img src="https://i.imgur.com/NwlA35L.png">](https://i.imgur.com/NwlA35L.png)

* test ping -f

[<img src="https://i.imgur.com/L30NEmA.png">](https://i.imgur.com/L30NEmA.png)

* if i update my desired capacity from 1 to 2:

[<img src="https://i.imgur.com/5N8ICuA.png">](https://i.imgur.com/5N8ICuA.png)

* New instance template (created): 

[<img src="https://i.imgur.com/RKgpWWw.png">](https://i.imgur.com/RKgpWWw.png)

* Automatic Registered targets:

[<img src="https://i.imgur.com/rhAI7vV.png">](https://i.imgur.com/rhAI7vV.png)

* Browser:

[<img src="https://i.imgur.com/lsBF27b.png">](https://i.imgur.com/lsBF27b.png)
