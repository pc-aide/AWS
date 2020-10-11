# VPC

## Acronym
* VPC - Virtual Private Cloud
* RDS - Relational Database Service
* ELB - Elastic Load Balancer
* SG - Security Group
* ENI - Elastic Network Interface
* IAM - Identity & Access Management
* NAT - Network Address Translation
* AZ - Availability Zone

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
[<img src="https://i.imgur.com/Jy35A6i.png">](https://i.imgur.com/Jy35A6i.png)

---

## Demo
* Create funtion
    * RadioButton: Author
    * Functiona name: Lambda-VPC
    * Runtime: python
* create funtion

[<img src="https://i.imgur.com/FnfUB8R.png">](https://i.imgur.com/FnfUB8R.png)

* Edit VPC:
    * VPC: default (for demo)
    * Subnets: .. - we want a subnet to access internet (for demo don't care)
    * SGs: default
    * Error (IAM Role):
````txt
The provided execution role does not have permissions to call CreateNetworkInterface on EC2
````

[<img src="https://i.imgur.com/AfjPPCv.png">](https://i.imgur.com/AfjPPCv.png)
[<img src="https://i.imgur.com/QQk0aH8.png">](https://i.imgur.com/QQk0aH8.png)

* IAM Role\Lambda-VPC 
    * attach policies\filter\ENI
    
[<img src="https://i.imgur.com/i4hl6zD.png">](https://i.imgur.com/i4hl6zD.png)


* Edit again the Lambda\VPC:

[<img src="https://i.imgur.com/uVgCFPT.png">](https://i.imgur.com/uVgCFPT.png)

* Test our function

[<img src="https://i.imgur.com/DwRkmAZ.png">](https://i.imgur.com/DwRkmAZ.png)
[<img src="https://i.imgur.com/xKwcFJS.png">](https://i.imgur.com/xKwcFJS.png)

* Check out if ENI will be created
* EC2\Network Interfaces
    * 2x ENI but i have 3x AZs !?
    
[<img src="https://i.imgur.com/n1v4VRt.png">](https://i.imgur.com/n1v4VRt.png)
[<img src="https://i.imgur.com/WH8ej1p.png">](https://i.imgur.com/WH8ej1p.png)
