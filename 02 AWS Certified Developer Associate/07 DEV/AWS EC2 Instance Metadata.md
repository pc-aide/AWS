# AWS EC2 Instance Metadata

## Doc

## Acronym

## Intro
* AWS Ec2 Instance Metadata is powerful but one of the least known **features** to developers
* It allows AWS EC2 instances to "learn about themselves" **without using an IAM Role** for that purpose
* The URL is **http://169.254.169.254/latest/meta-data**
    * curl -s http://169.254.169.254/latest
    * curl -s http://169.254.169.254/latest/meta-data/placement/availability-zone
* You can retrieve the IAM Role name from the metadata, but your CANNOT retrieve the IAM Policy
* Metadata = Info about the EC2 instance
    
[<img src="https://i.imgur.com/ysXidrM.png">](https://i.imgur.com/ysXidrM.png)
[<img src="https://i.imgur.com/JGbhFyr.png">](https://i.imgur.com/JGbhFyr.png)
[<img src="https://i.imgur.com/755T59W.png">](https://i.imgur.com/755T59W.png)

* O/P: 
````text
ami-id
ami-launch-index
ami-manifest-path
block-device-mapping/
events/
hostname
iam/
identity-credentials/
instance-action
instance-id
instance-life-cycle
instance-type
local-hostname
local-ipv4
mac
metrics/
network/
placement/
profile
public-hostname
public-ipv4
public-keys/
reservation-id
security-groups
````
