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
