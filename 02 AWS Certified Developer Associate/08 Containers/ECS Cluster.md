# ECS Cluster

## Acronym
* ECS - Elastic Container Service
* AMI - Amzon machine image
* HA - High Available
* SG: Security Group

## Doc

## Intro
* ECS Clusters are logical grouping of EC2 instances
* EC2 instances run the **ECS agent** (Docker container)
* The ECS agent registers the instance to the ECS cluster
* The EC2 instances run a special AMI, made specifically for ECS

### Diagram
[<img src="https://i.imgur.com/0b62rPS.png">](https://i.imgur.com/0b62rPS.png)

---

## Demo
* Go to ECS\get started & cancel, we don't want to use Fargate:

[<img src="https://i.imgur.com/yFdpEaq.png">](https://i.imgur.com/yFdpEaq.png)
[<img src="https://i.imgur.com/N9Onrzp.png">](https://i.imgur.com/N9Onrzp.png)

* Create Cluster:
    * Select cluster template: EC2 Linux + networking
    
[<img src="https://i.imgur.com/bDa2h7H.png">](https://i.imgur.com/bDa2h7H.png)

* Cfg cluster 
    * Cluster name: demo-cluster
    * EC2 instance type: t2.micro
    * EC2 Ami Id: Amazon Linux 1 AMI [ami-04bed016024638f1d]
    
[<img src="https://i.imgur.com/NF8BFiT.png">](https://i.imgur.com/NF8BFiT.png)

* Cfg networking
    * VPC: default
    * Subnet: 3x subnets (for HA)
    * SG: SG-ECS-Cluster-IN
    
[<img src="https://i.imgur.com/fTVEQCd.png">](https://i.imgur.com/fTVEQCd.png)

* Cfg IAM Role:
      * Container instance IAM role: Create new role (automatic)
````text
You are giving permission to Elastic Container Service to create and use ecsInstanceRole.
````

[<img src="https://i.imgur.com/xfjtwKH.png">](https://i.imgur.com/xfjtwKH.png)

* Create
* Provision...:

[<img src="https://i.imgur.com/JKr5gGN.png">](https://i.imgur.com/JKr5gGN.png)
[<img src="https://i.imgur.com/zJOA0Za.png">](https://i.imgur.com/zJOA0Za.png)

* IAM (new one automatic) role:

[<Img src="https://i.imgur.com/gs5jQHW.png">](https://i.imgur.com/gs5jQHW.png)
[<img src="https://i.imgur.com/OYr8Fve.png">](https://i.imgur.com/OYr8Fve.png)
