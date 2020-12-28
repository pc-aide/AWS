# Interface Endpoints

## Acronym
* AZ - Availability Zone
* CW - CloudWatch 
* DNS - Domain Name System
* S2S - Site To Site
* VPN - Virtual Private Network

## Intro
1) Select VPC, subnets, & service for interface
2) Attach an endpoint policy to the endpoint
3) Enable private DNS if desired
* One subnet per AZ
* Multiple DNS entries
* Use AZ IDs for cross account
* Interface endpoint request must be accepted  
* Charge per interface

---

## Limitations
* One subnet per AZ
* Endpoints support IPv4 & same region only
* Endpoints can be extended with S2S VPN & Direct Connect
* DNS resolution must be enabled

---

## Console
* Endpoint type
  * Interface
* Service name: *.logs (CW logs)
  
[<img src="https://i.imgur.com/6viwpA1.png">](https://i.imgur.com/6viwpA1.png)
[<img src="https://i.imgur.com/LuAApUO.png">](https://i.imgur.com/LuAApUO.png)

* DNS names

[<img src="https://i.imgur.com/TSQAQKB.png">](https://i.imgur.com/TSQAQKB.png)
