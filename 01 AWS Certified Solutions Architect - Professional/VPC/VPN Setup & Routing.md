# VPN Setup & Routing

## Acronym
* ASN - Autonomous System Number
* BGP - Border Gateway Protocol
* CIDR - Classless Inter-Domain Routing
* CGW - Costomer Gateway
* HA - High Availability
* VGW - Virtual Private Gateway

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

## Site to Site VPN (AWS Managed VPN)
* On-premise:
  * Setup a software or hardware VPN applicance to your on-premise network
  * The on-premise VPN should be accessible using a public IP
* AWS-side:
  * Setup a VGW & attach to your VPC
  * Setup a Customer Gateway to point the on-premise VPN appliance
* Two VPN connection (tunnetls) are created for redundancy, encrypted using IPSec
* Can optionally accelerate it using Global Accelerator (for worldwide networks)
  
### Diagram
[<img src="https://i.imgur.com/jlWMtDC.png">](https://i.imgur.com/jlWMtDC.png)

---

## Route Propagation in Site-to-Site VPN
* Static Routing:
  * Create static route in corporate data center for 10.0.0.1/24 through the CGW
  * Create static route in AWS for 10.3.0.0/20 through the VGW
* Dynamic Ruting (BGP):
  * Uses BGP to share routes automatically (eBGP for internet)
  * We don't need to update the routing tables, it will be done for use dynamically
  * Just need to specify the ASN of the CGW & VGW
  
### Diagram
[<img src="https://i.imgur.com/Ahtwt94.png">](https://i.imgur.com/Ahtwt94.png)

---

## Site to Site VPN & Internet Access
* **Not okay** (blocked by **NAT Gateway** restrictions)
* **Okay** (self managed **NAT Instance** - more control)

### Diagram
[<img src="https://i.imgur.com/VGCvNCI.png">](https://i.imgur.com/VGCvNCI.png)

[<img src="https://i.imgur.com/F5F1QSQ.png">](https://i.imgur.com/F5F1QSQ.png)

