# VPC

## Acronym
* AZ - Availability Zone
* CW - CloudWatch
* ENI - Elastic Network Interface
* HA - High Availability
* IGW - Internet Gateway
* NACL - Network Access Control List
* NAT - Network Address Translation
* SG - Security Group
* SSM - System Manager
* VPC - Virtual Private Cloud

## Core Components
* Subnets
* Route Tables
* Endpoints
* Gateways (if you want to get outside of your VPC)
  * NAT Gateways
    * Managed NAT solution, bandwidth scales automatically
    * Resilient to failure within a single AZ
    * Must deploy multiple NAT Gateways in multiple AZ for HA
  * Internet Gateways
    * helps our VPC connect to the internet, HA, scales horizontally
    * Acts as a NAT for instances that have a public IPv4 or public IPv6
    * Has an Elastic IP, external services see the IP of the NAT Gateway as the source
  * Endpoint Gateways
* SGs
  * Statefull = return traffic is automatically allowed, regedless of rules
* NACLs (Firewall rules)
  * Stateless = return traffic must be explicitly allowed by rules
* NAT Instances
  * EC2 instance you deplploy in a public subnet
  * Edit the route in your private subnet to route 0.0.0.0/0 to your NAT instance
  * Not resilient to failure, limited badwidth base on instance type, cheap
  * Must manage failover yourself
* VPC Flows Logs
  * Log internet traffic going through your VPC
  * Can be defined at the **VPC** level, **Subnet** level, or **ENI**-level
  * Helpful to capture "denied internet traffic"
  * Can be sent to CW Logs & S3
* **Bastion Hosts**
  * SSH into private EC2 instances through a public EC2 instance (bastion host)
    * 2x SSH
  * you must manage these instances yourself (failover,recovery)
  * SSM Session Manager is a more secure way to remote control without SSH

### Diagram
* NAT Gateway: 

[<img src="https://i.imgur.com/OdlJqB2.png">](https://i.imgur.com/OdlJqB2.png)

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
