# Endpoints

## Acronym
* ENI - Elastic Network Interface
* IGW - Internet Gateway
* NAT - Network Address Translation
* S3 - Simple Storage Service

## Intro
* Regional endpoints
* VPC endpoints
* Secure access to AWS services
  * No IGW, NAT device, VPN connection
  * No public IP address
  * Does not leave Amazon network
* Gateway or interface
  * S3 & DynamoDB for gateway
  * AWS PrivteLink interface for others
* Endpoints allow you to connect to AWS Services using a private network instead of the public www network
* They scale horizontally & are redundant
* No more IGW, NAT, etc... to access AWS Services
* VPC Endpoint Gateway (S3 & DynamoDB)
* VPC Endpoint Interface (the rest)
* In case of issues:
  * Check DNS Setting Resolution in your VPC
  * Check Route Tables

### Diagram
[<img src="https://i.imgur.com/92WfbWy.png">](https://i.imgur.com/92WfbWy.png)

---

## 
