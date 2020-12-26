# ENIs

## Acronym
* AZ - Availability Zone
* ENI - Elastic Network Interface
* EIP - Elastic IP

## Intro
* Subnet based
* Multiple private IPv4 addresses
* Multiple IPv6 addresses
* One EIP address per private
* One public IPv4 address per interface
* Used by instances & gateways
* Performance based on instance type
  * e.g.
    * t2.micro
    
---

## EC2 Networking
* EC2 instances always have an ENI
* **primary ENI is eth0** & can't be removed
* Secondary ENIs can be attached
* All instance ENIs must be in same AZ

### Diagram
* ENIs
  * eth0 Public
   * 10.0.1.5
   * 10.0.1.10
   * 10.0.1.6
 * eth1 Private
  * 10.0.0.4.5
  
[<img src="https://i.imgur.com/aBCJpGJ.png">](https://i.imgur.com/aBCJpGJ.png)
