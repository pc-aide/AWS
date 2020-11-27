# Bloking an IP Address

## Doc
* [Network ACLs](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-network-acls.html)

## Acronym
* NACL - Network Access Control List
* SG - Security Group
* NLB - Network Load Balancer
* WAF - Web Application Firewall
* ALB - Application Load Balancer

## Scenarios
### 01 - NACL (Basic)
* NACL & SG are free

[<img src="https://i.imgur.com/28a7rNA.png">](https://i.imgur.com/28a7rNA.png)

### 02 - ALB
[<img src="https://i.imgur.com/z3kQ9jT.png">](https://i.imgur.com/z3kQ9jT.png)

### 03 - NLB
* No SG
* Traffic goes through

[<img src="https://i.imgur.com/JfDV87X.png">](https://i.imgur.com/JfDV87X.png)

### 04 - ALB + WAF
* Much expensive, additional service, WAF
* Much over power of security

### 05 - ALB, CloudFront WAF
* No NACL, not helpful

[<img src="https://i.imgur.com/p8NEO9r.png">](https://i.imgur.com/p8NEO9r.png)
