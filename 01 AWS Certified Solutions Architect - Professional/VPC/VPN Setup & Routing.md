# VPN Setup & Routing

## Acronym
* BGP - Border Gateway Protocol
* CIDR - Classless Inter-Domain Routing
* HA - High Availability
* VGW - Virtual Gateway

## Steps
1) Create a Virtual privte gateway & attach to VPC
2) Create a customer gateway
3) Create a site-to-side VPN connection
4) Configure routing

---

## VPN Routing
* Static or dynamic routing via BGP
* BGP is preferred for routing & HA
* Route tables can ingest propagated routes
* Route preference (more specific wins)
  * Local
  * BGP from Direct Connect
  * Static to VGW
  * As Path & MED as tie breaker
  
### Diagram
[<img src="https://i.imgur.com/faHCS05.png">](https://i.imgur.com/faHCS05.png)

---

## Transit VPC (=Software VPN)
* Not an AWS offering, newer managed solution is Transit Gateway
* Use the public internet with a software VPN solution 
* Allows for transitive connectivity between VPC & locations
* More complex routing rules, overlapping CIDR ranges, network-level packet filtering

### Diagram
[<img src="https://i.imgur.com/HrhKLBF.png">](https://i.imgur.com/HrhKLBF.png)

---

## Network topologies can become complicated
[<img src="https://i.imgur.com/TV7kWN4.png">](https://i.imgur.com/TV7kWN4.png)

---
