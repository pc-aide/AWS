# VPC

## Acronym
* VPC - Virtual Private Cloud
* RDS - Relational Database Service
* ELB - Elastic Load Balancer
* SG - Security Group
* ENI - Elastic Network Interface
* IAM - Identity & Access Management
* NAT - Network Address Translation

## Doc

## Lambda by default
* By default, your Lambda function is launched outside your own VPC (in an
  AWS-owned VPC)
* Therefore it can't access resources in your VPC (RDS, ElastiCache, internal ELB...)

### Diagram
[<img src="https://i.imgur.com/o4TWTxj.png">](https://i.imgur.com/o4TWTxj.png)

---

## Lambda in VPC
* You must define the VPC ID, the Subnets & the SGs
* Lambda will create an ENI in your subnets
* IAM Role:
    * **AWSLamdaVPCAccessExectuionRole**
    
### Diagram
[<img src="https://i.imgur.com/Dpwvchu.png">](https://i.imgur.com/Dpwvchu.png)

---

## Internet Access
* A Lambda function in your VPC does not have internet access
* **Deploying a Lambda function in a public subnet does not give it internet
  access or a public IP**
* Deploying a Lambda function in a private subnet gives it inernet access if
  you have **NAT Gateway/Instance**
* You can use **VPC endpoints** to privately access AWS service without a NAT
  
### Diagram
[<img src="https://i.imgur.com/38xA7pI.png">](https://i.imgur.com/38xA7pI.png)
