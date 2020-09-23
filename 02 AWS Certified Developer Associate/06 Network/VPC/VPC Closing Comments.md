# VPC Closing Comments

## Acronym
* VPC - Vitual Private Cloud
* AZ - Availability Zone
* IGW - Internet Gateway
* SG - Security Group
* ENI - Elastic Network Interface
* DC - Domain Controller

## Doc

## Introduction
* VPC
* Sunets: tied to an AZ, network partition of the VPC
* IGW: at the VPC level, provide Internet Access
* NAT Gateway / Instance: give internet access to private subnets
* NACL: Stateless, subnet rules for inbound & outbound
* SGs: Stateful, operate at the EC2 instance level of ENI
* VPC Peering: Connect two VPC with non overlapping IP ranges, non transitive
* VPC Endpoints: Provide private access to AWS Services within VPC
* VPC Flow Logs: network traffic logs
* Site to Site VPN: VPN over public internet between on-premises DC & AWS
* Direct Connect: direct private connection to a AWS  
