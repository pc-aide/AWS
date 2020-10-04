# CodeBuild in VPC

## Acronym
* VPC - Virtual Private Cloud
* SG - Security Group
* RDS - Relational Database Service
* ALB - Application Load Balancer
* LB - Load Balancers

## Doc

## Intro
* By default, your CodeBuild containers are lanched outside your VPC
* Therefore, by default it cannot access resources in a VPC
    * Ex: codeBuild can't acces RDS (private subnet)
* You can specify a VPC configuration:
    * VPC ID
    * Subnets IDs
    * SG IDs
* Then your build can access resources in your VPC (RDS, ElastiCache, EC2, ALB..)
* Use cases: integration test, data query, internal LBs

### Diagram
[<img src="https://i.imgur.com/gqlWmVA.png">](https://i.imgur.com/gqlWmVA.png)

---

## Demo
* Build project\Edit\Environment
* I can modify the VPC

[<img src="https://i.imgur.com/9V1drX2.png">](https://i.imgur.com/9V1drX2.png)

* Add. config
      * VPC
      
[<img src="https://i.imgur.com/E3mIvG2.png">](https://i.imgur.com/E3mIvG2.png)
