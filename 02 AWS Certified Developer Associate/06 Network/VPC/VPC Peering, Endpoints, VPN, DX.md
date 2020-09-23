# VPC Peering, Endpoints, VPN, DX

## Acronym
* VPC - Virtual Private Cloud
* VPN - Virtual Private Network
* CIDR - Classless inter-domain routing
* DX - Direct Connect

## Doc

## VPC Peering
* **Connect two VPC**, privately using AWS' network
* Make them behave as if they were in the same network
* Must not have overlapping CIDR (IP address range)
* VPC Peering connection is **not transitive** (must be established for each VPC that need to communicate with one another)

### Diagram
[<img src="https://i.imgur.com/gmuR2ae.png">](https://i.imgur.com/gmuR2ae.png)
[<img src="https://i.imgur.com/qbcrazj.png">](https://i.imgur.com/qbcrazj.png)

---

## VPC Endpoints
* Endpoints allow you to connect to AWS Services **using a private network** instead of the public www network
    * e.x: EC2 with subnet private & we need that this instance to acces a AWS service public (S3, DynamoDB, etc)
* This give you enhanced security & lower latency to access AWS services
* VPC Endpoint Gateway: S3 & DynamoDB
* VPC Endpoint Interface: the rest
* <ins>Only used within your VPC</ins>

### Diagram
[<img src="https://i.imgur.com/CxAbZCd.png">](https://i.imgur.com/CxAbZCd.png)

---

## Site to Site VPN & Direct Connect
* Site to Site VPN
  * Connect an on-premises VPN to AWS
  * The connection is automatically encrypted
  * Goes over the public internet
* Direct Connect (DX)
  * Establish a physical connection between on-premises & AWS
  * The connection is private, secure & fast
    * You ask to your ISP to get a single network for you to connect to AWS
  * Goes over a private network
  * Takes at least a month to establish
* Note: Site-to-site VPN & Direct Connect cannot access VPC endpoints
  
  
## Diagram
* ex: SRX340 (MSSS) <--> SRX100 (GMF-Cap-Rouge)

[<img src="https://i.imgur.com/GVJH1jo.png">](https://i.imgur.com/GVJH1jo.png)
