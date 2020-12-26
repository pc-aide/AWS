# VPC

## Acronym
* VPC - Virtual Private Cloud
* SG - Security Group
* NACL - Network Access Control List

## Core Components
* Subnets
* Route Tables
* Endpoints
* Gateways (if you want to get outside of your VPC)
  * NAT Gateways
  * Internet Gateways
  * Endpoint Gateways
* SGs
* NACLs (Firewall rules)

---

## IP addressing
* VPC IP address range is 
  * **/16 to /28**
    * /16 = 65k address
* RFC 1918 preferred
* Five reserver subnet addresses
  * +0: network address
    * e.g. 192.168.0.0/24 - network address
  * +1: VPC router - traffic needs to be routed arount, the VPC (as gateway)
  * +2: DNS server
  * +3: reserved - AWS doesn't know what the ywant to use it for
  * +last: broadcast address
