# Transit Gateway

## Doc
* [Creating a single internet exit point from multiple VPCs Using AWS Transit Gateway](https://aws.amazon.com/blogs/networking-and-content-delivery/creating-a-single-internet-exit-point-from-multiple-vpcs-using-aws-transit-gateway/)

## Acronym
* EFS - Elastic File System
* NAT - Network Address Translation
* NLB - Network Load Balancer
* RAM - Resource Access Manager
* TGW - Transit Gateway
* VPC - Virtual Private Cloud

## Intro
* For having transitive peering between thousands of VPC & on-premise, hub-and-spoke (start) connection
* Regional resource, can work cross-region
* Share cross-accoung using RAM
* You can peer Transit Gateway across region
* Route Tables: limit which VPC can talk with other VPC
* Works with Direct Connect Gateway, VPN connections
* Supports **IP Multicast**( not supported by any other AWS service)
* Instances in a VPC can access a NAT Gateway, NLB, PrivateLink, & EFS in others VPCs attached to the AWS Transit Gateway
* Regional virtual router
* Supported connections:
  * VPCs
  * VPN connections
  * Direct Connect gateways
  * Transit gateway peering
* Cross-account support
* Managed by AWS

### Diagram
[<img src="https://i.imgur.com/IEU7TlK.png">](https://i.imgur.com/IEU7TlK.png)
[<img src="https://i.imgur.com/XYmHGUP.png">](https://i.imgur.com/XYmHGUP.png)

---

## Central NAT Gateway
* The NAT Gateway is shared in the Egress-VPC
* The private App VPC can access internet through the TGW
* In this example: the App VPCs can't communicate with each other based on the TGW route table

### Diagram
[<img src="https://i.imgur.com/JMMU3ne.png">](https://i.imgur.com/JMMU3ne.png)
