# WAF & Shield

## Doc
* [Security (White paper)](https://d1.awsstatic.com/whitepapers/Security/DDoS_White_Paper.pdf)

## OSI 7 Layer Model
* Layer 3 -> Network -> e.g -> packets -> IP, ICMP
* Layer 4 -> Transport -> e.g -> TCP, UDP
* Layer 7 -> Application -> end user -> e.g -> SMTP -> level exploit on process

[<img src="https://i.imgur.com/keR5lyG.png">](https://i.imgur.com/keR5lyG.png)

## Acronym
* WAF - Web Application Firewall
* ALB - Application Load Balancer
* CLB - Classic Load Balancer
* DRP - Disaster Response Program
* ACL - Access Control List
* EIP - Elastic IP
* ELB - Elastic Load Balancer
* DDoS - Distributed Deny of Service
* SMTP - Simple Mail Tranfer Protocol
* VPC - Virtual Private Cloud
* RDS - Relational Database Service
* VPC - Virtual Private Cloud
* SG - Security Group
* CIDR - Classes Inter-Domain Routing
* ENI - Elastic Network Interface
* NACL - Network ACL
* ACL - Access Control List

## Network Security
* SGs
  * Attached to ENI - EC2, RDS, Lambda in VPC, etc
  * Are stateful (any traffic in is allowed to go out, any traffic out can go back in)
  * Can reference by CIDR & SGID
  * Supports SG references for VPC peering
  * Default: inbound denied, outbound all allowed
* NACL
  * Attached at the subnet level
  * Are stateless (inbound <ins>&</ins> outbound rules apply for all traffic)
  * Can only  reference a CIDR range (no hostname)
  * Default: allow all inbound, allow all outbound
  * New NACL: denies all inbound, denies all outbound
* Host Firewall
  * EC2

  
### Diagram
[<img src="https://i.imgur.com/VZg0xk8.png">](https://i.imgur.com/VZg0xk8.png)

---

## What's a DDoS Attach ?
[<img src="https://i.imgur.com/KZzwaDh.png">](https://i.imgur.com/KZzwaDh.png)

---

## Type of Attacks on your infrastructure
* DDoS
  * When your service is unavailable because it's receiving too many requests
  * SYN Flood (layer 4): send too many TCP connection requests
  * UDP Reflection (Layer 4): get other servers to send many big UDP request
  * DNS flood attack: overwhelm the DNS so legitimate users can't find the site
  * Slow Loris attack: a lot of HTTP connections are opened & maintaned
* Application level attacks:
  * more complex, more specific (HTTP level)
  * Cache bursting strategies: overload the backend database by invalidating cache
  
---

## DDoS Protection on AWS
* **Shield Standard**: protects against DDoS attack for your website & applications, for all customers at no additional costs
* **Shield Advanced**: 24/7 premium DDoS protection
* **WAF**: Filter specific requests based on rules
* CloudFront & Route 53:
  * Default have Shield enabled
  * Availability protection using global edge network
  * Combined with Shield, provides DDoS attack mitigation at the edge
* Be ready to scale - leverage Auto Scaling
* Separate static resources (s3/CloudFront) from dynamic ones (EC2/ALB)

---

## Sample Reference Architecture
[<img src="https://i.imgur.com/rjJKf6c.png">](https://i.imgur.com/rjJKf6c.png)

---

## Shield
1) Shield Standard:
  * **Free** service that is activated for every AWS customer
  * Provides protection fron attacks such as **SYN/UDP Floods**, **Reflection** attacks & other layer 3 (network), layer 4 (transport) attacks
2) Shield Advanced:
  * Optional DDoS mitigation service (**3k$ /month** per organization)
  * Protect against more sophisticated attack on EC2, ELB, CloudFront, Global Accelerator, & Route 53
  * 24/7 access to DDoS response team (DRP)
  * Protect against higher fees during usage spikes due to DDoS
  
---

## WAF
* Protects your web applications from common web exploits (Layer 7 - Application)
* Deploy on **ALB** (lolocalized rules)
* Deploy on **API Gateway** (rules running at the regional or edge level)
* Deploy on **CloudFront** (rules globally on edge locations)
  * Used to front other solutions: CLB, EC2 instances, custom origin, S3 websites
* <ins>WAF is not for DDoS protection</ins>
* Define Web ACL
  * Rules can include: **IP addresses**, HTTP headers, HTTP body, or URI strings
  * Protects from common attack - **SQL injection** & Cross-Site Scripting (XSS)
  * Size constraints, Geo match
  * Rate-based rules (to count occurrences of events)

---

## Firewall Manager
* Manage rules in all accounts of an AWS Organization
* Common set of security rules
* WAF rules (ALB, API Gateway, CloudFront)
* Shield Advanced (ALB, CLB, EIP, CloudFront)
* SGs for EC2 & ENI resources in VPC
