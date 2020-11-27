# WAF & Shield

## Acronym
* WAF - Web Application Firewall
* DDoS - Distributed Deny of Service
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
