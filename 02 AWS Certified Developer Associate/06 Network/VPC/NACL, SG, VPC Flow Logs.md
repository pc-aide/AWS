# NACL, SG, VPC Flow Logs

## Doc
* [https://docs.aws.amazon.com/vpc/latest/userguide/what-is-amazon-vpc.html](https://docs.aws.amazon.com/vpc/latest/userguide/what-is-amazon-vpc.html)

## Acronym
* NACL - Network Access Control List
* SG - Security Group
* VPC - Virtual Private Cloud
* ENI - Elastic Network Interface
* ELB - Elastic Load Balancing

## NACL & SGs
* NACL
  * A **firewall** which controls traffic from & to subnet
  * Can have ALLOW & DENY **rules**
  * Are attached at the **Subnet** level
  * Rules only include **IP** addresses
* SGs
  * A firewall that controls traffic to & from **an ENI / an EC2 Instance**
  * Can have **ALLOW** rules
  * Rules include IP addresse & other SGs

### Diagram
[<img src="https://i.imgur.com/zG4hUEc.png">](https://i.imgur.com/zG4hUEc.png)

---

## Table
 Secruity Group                                                                                                                             | NACL                                                                                                                                            |
| ------------------------------------------------------------------------------------------------------------------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------- |
| Operates at the **instance** level                                                                                                             | Operates at the **subnet** level                                                                                                                    |
| Supports **allow** rules only                                                                                                                  | Supports **allow** rules & **deny** rules                                                                                                               |
| Is strateful: **Return traffic is automatically** allowed, regardless of any rules                                                             | Is stateless: **Return traffic must be explicitly** allowed by rules                                                                                |
| We evaluate all rules before deciding wheter to allow traffic                                                                              | We process rules in number order when deciding whether to allow traffic                                                                         |
| Applies to an instance only if someone specifies<br>the SG when launching the instance,<br>or assocaites the SG with the instance later on | Automatically applies to **all instance in the<br>subnets** it's associated with (therefore, you<br>don't have to rely on susers to specify the SG) |

---

## VPC Flow Logs
* Capture information about IP traffic going into your interfaces
  * VPC Flow logs
  * Subnet Flow logs
  * Elastic Network Interface Flow Logs
* Helps to monitor & troubleshoot connectivity issues ex:
  * Subnets to internet
  * Subnets to subnets
  * Internet to subnets
* Captures network information from AWS managed interfaces too: ELBs, ElastiCache, RDS, Aurora, etc...
* VPC Flow logs data can go to S3 / CloudWatch Logs
