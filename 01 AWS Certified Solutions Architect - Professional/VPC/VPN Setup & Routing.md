# VPN Setup & Routing

## Acronym
* ASN - Autonomous System Number
* BGP - Border Gateway Protocol
* CIDR - Classless Inter-Domain Routing
* CGW - Costomer Gateway
* HA - High Availability
* VGW - Virtual Private Gateway
* VPN - Virtual Private Network

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
* **Okay** (alternative to NAT Instances/Gateway)

### Diagram
[<img src="https://i.imgur.com/VGCvNCI.png">](https://i.imgur.com/VGCvNCI.png)

[<img src="https://i.imgur.com/F5F1QSQ.png">](https://i.imgur.com/F5F1QSQ.png)

[<img src="https://i.imgur.com/N6yxX71.png">](https://i.imgur.com/N6yxX71.png)

---

## AWS VPN CloudHub
* Can connect up to 10 Customer Gateway for each VGW
* Low cost hub-and-spoke model for primary or secondary network connectivity between locations
* Provide secure communication between sites, if you have multiple VPN connections
* It's a VPN connection so it goes over the public internet
* Can be a **failover connection** between your on-premise locations

### Diagram
[<img src="https://i.imgur.com/8MKjAGc.png">](https://i.imgur.com/8MKjAGc.png)

---

## AWS Client VPN
* Connect from your computer using OpenVPN to your privte network in AWS & on-premise

### Diagram
[<img src="https://i.imgur.com/LKBZQFZ.png">](https://i.imgur.com/LKBZQFZ.png)

---

## Software VPN (not AWS managed)
* You can setup your own software VPN, but you have to manage everything including badwidth, redundancy, etc.
* You would have more control over the setup & routing options

### Diagram
[<img src="https://i.imgur.com/snzaIPk.png">](https://i.imgur.com/snzaIPk.png)

---

## VPN to multiple VPC
* For VPN-based customers, AWS recommends creating a separate VPN connection for each customer VPC
* Direct Connect is recommended because it has a Direct Connect Gateway

### Diagram
[<img src="https://i.imgur.com/yj6a44y.png">](https://i.imgur.com/yj6a44y.png)

---

## Shared Services VPC
* Create a VPN connection between on-premise & shared service VPC
* Replicate services, applications, databases between on-premise & the Shared Services VPC or deploy proxies in the shared service VPC
* Do VPC peering between the VPC & the shared service VPC
* VPCs can directly access the Shared Service VPC services & don't need VPN connection to on-premise

### Diagram
[<img src="https://i.imgur.com/ywihRVj.png">](https://i.imgur.com/ywihRVj.png)

---

## Other Solutions
* Transit VPC (complicated)
  * Good for resources that are hard to replicate on the cloud
  * Must use VPN as VPC peering does not support transitive routing
  
### Diagram
* Transit VPC:

[<img src="https://i.imgur.com/VdaJ4Oa.png">](https://i.imgur.com/VdaJ4Oa.png)

* Transit Gateway (simple):

[<img src="https://i.imgur.com/awA0oGB.png">](https://i.imgur.com/awA0oGB.png)
