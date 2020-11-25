# SSL on ELB

## Acronym
* ALB - Application Load Balancer
* SSM - System Manager
* ELB - Elastic Load Balancer
* NLB - Network Load Balancer
* ACM - AWS Certificate Management
* AZ - Availability Zone
* SSL - Security Sockets Layer
* CU - Cryptographic User
* HSM - Hardware Security Module

## SSL on ALB
* SSL on ALB:

[<img src="https://i.imgur.com/iGQ14U7.png">](https://i.imgur.com/iGQ14U7.png)

---

## SSL on web server EC2 instances
* SSL on EC2: 

[<img src="https://i.imgur.com/RFSAIE2.png">](https://i.imgur.com/RFSAIE2.png)

---

## SSL Offloading
* You can offload SSL to CloudHSM (SSL Acceleration)
* Supported by NGINX & Apache Web servers
* Extra security: the SSL private key never leaves the HSM device
* Must setup a cryptographic user (CU) on the CloudHSM device

### Diagram
[<img src="https://i.imgur.com/2g5Tf71.png">](https://i.imgur.com/2g5Tf71.png)
