# Virtual Private Cloud 

## Acronym
* VPC - Virtual Private Cloud
* HA - High Availability
* AZ - Availability Zone
* IGW - Internet Gateway
* NAT - Network Address Translation
* NACL - Network Access Control Lists

## Doc
* https://aws.amazon.com/vpc/

## Intro
* A private, virtual network in the AWS Cloud
  * Uses same concepts as on premise network 
    * A VPC defines an IP address space

* All Subnets 
  * By Default, all subnets within a VPC can communicate with each other

*Allows complete control of network configuration
  * Abilitty to isolate & expose resources inside VPC
  
* Offers several layers security of controls 
    * To allow & deniy specific internet & internal traffic

* Other AWS service deploy into VPC
    * Services inherent security build into network
    
* Services
  * EC2
  * EMR
  * RDS
  * WorkSpaces
  * Elastic Load Balancing
  * OpsWorks 
  * EFS
  * Elastic Beanstalk
  * Route 53
  * Data Pipeline
  * S3
  * DynamoDB
  * ElastiCache
  
[<img src="https://i.imgur.com/ayNQjoh.png">](https://i.imgur.com/ayNQjoh.png)

* Features
  * Builds upon HA of AWS Regions & AZ
    * Amazon VPC lives within a Region
    * Multiple VPCs per account
  * Subnets
    * Used to divide Amazon VPC
    * Allows Amazon VPC to span multiple AZs
  * Route tables
    * Control traffic going out of the subnets
  * IGW
    * Allows acces to the Internet from Amazon VPC
  * NAT Gateway
    * Allows private subnet resources to access Internet
  * NACL
    * Control access to subnet; stateless

[<img src="https://i.imgur.com/q0tQO4l.png">](https://i.imgur.com/q0tQO4l.png)

# E.g.
[<img src="https://i.imgur.com/RltUeNz.png">](https://i.imgur.com/RltUeNz.png)

## Demo
[<img src="https://i.imgur.com/l4oLe11.png">](https://i.imgur.com/l4oLe11.png)
[<img src="https://i.imgur.com/b7u7yjJ.png">](https://i.imgur.com/b7u7yjJ.png)
* Idem AZ
* No ping between 2 hosts
  * Event if wf.msc\{inbound,outbound} enabled ICMPv4
   * Because it's firewall -> aws security-group
    * Only RDP (SG : Inbound.RDP & Oubound all traffic)
     * Solution: sg-ICMPv4_Inbount_Request (echo) + VPC peering connection
