# DNS

## Acronym
* CIDR - Classless Inter-Domain Routing
* DNS - Domain Name System
* bool - boolean
* VPC - Virtual Private Cloud

## Intro
* 2x options for DNS
  1) DNS by AWS
    * Route 53 external
    * Private Hosted Zone (Cost: $0.5 / entry)
  2) Bring your own DNS
    * Private DNS servers
    * Public DNS service
    
---

## Amazon Provided DNS
* VPC DNS attributes
  * enableDNSHostnames - bool
  * enableDNSSupport - bool
  * Default VPC both true
  * Custom VPC enableDnsSupport true
* Hostname resolution
  * +2 of subnet CIDR
  * Instance Metadata Service
  
[<img src="https://i.imgur.com/HLXRtA4.png">](https://i.imgur.com/HLXRtA4.png)

### Diagram
[<img src="https://i.imgur.com/hGm2GD3.png">](https://i.imgur.com/hGm2GD3.png)


### Console
[<img src="https://i.imgur.com/P9YYISa.png">](https://i.imgur.com/P9YYISa.png)
