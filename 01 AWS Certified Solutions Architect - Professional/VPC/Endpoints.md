# Endpoints

## Acronym
* DX - Direct Connect
* ENI - Elastic Network Interface
* IGW - Internet Gateway
* NAT - Network Address Translation
* S3 - Simple Storage Service
* SG - Security Group
* TGW - Transit Gateway
* VPC - Virtual Private Cloud

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

## VPC Endpoint Gateway
* Only work for S3 & DynamoDB, must create one gateway per VPC
* Must update route tables entries
* Gateway is defined at the VPC level
* DNS resolution must be enabled in the VPC
* The same public hostname for S3 can be used
* Gateway endpoint can't be extended out of a VPC (VPN, DX, TGW, peering)

### Diagram
[<img src="https://i.imgur.com/WWcIIvv.png">](https://i.imgur.com/WWcIIvv.png)

---

## Interface
* Provision an ENI that will have a private endpoint interface hostname
* Leverage SGs for security
* Private DNS (setting when you create the endpoint)
  * The public hostname of a service will resolve to the private Endpoint Interface hostname
  * VPC Setting: "Enable DNS hostnames" & "Enable DNS Support" must be 'true'
  * Example for Athena:
    * vpc-0b7d2995e9dfe5418-mwrths3x.athena.us-east-1.vpce.amazonaws.com
    * vpc-0b7d2995e9dfe5418-mwrths3x-us-east-1a.athena.us-east-1a.vpce.amazonaws.com
    * vpc-0b7d2995e9dfe5418-mwrths3x-us-east-1a.athena.us-east-1b.vpce.amazonaws.com
    * **athena.us-east-1.amazonaws.com** (private DNS name)
* Interface can be accessed from Direct Connect & Site-to-Site VPN
