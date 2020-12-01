# Route 53

## Doc
* [Configuring DNSSEC for a domain](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/domain-configure-dnssec.html)
* [How do I associate a Route 53 private hosted zone with a VPC on a different AWS account?](https://aws.amazon.com/premiumsupport/knowledge-center/private-hosted-zone-different-account/)

## Acronym
* Domain Name System
* MITMA - Man In the Middle Attack
* CLB - Classic Load Balancer
* ALB - Application Load Balancer
* CW - CloudWatch
* RDS - Relational Database Service
* NLB - Network Load Balancer
* NS - NameServer
* ELB - Elastic Load Balancer
* DNS SEC - DNS Security Extension
* TTL - Time To Live
* EB - Elastic Beanstalk

## Records
* Route 53 is Managed DNS
* A: hostname to IPv4
* AAAA: hostname ot IPv6
* CNAME: hostname to hostname
* Alias: hostname to AWS resource
  * Use for: CLB, ALB, NLB, CloudFront, S3 bucket, EB
  * Can be used for root apex record (mydomain.com)
* Other record types are not needed for the exam

---

## Diagram for A Record  
[<img src="https://i.ibb.co/r5JDtyX/image.png">](https://i.ibb.co/r5JDtyX/image.png)

---

## DNS Records TTL
* High TTL (e.g. 24hr)
  * less traffic on DNS
  * Possibly outdated records
* Low TTL: (e.g. 60s)
  * More traffic on DNS
  * Records are outdated for less time
  * Easy to change records
* TTL is mandatory for each DNS records

### Diagram
[<img src="https://i.ibb.co/xXymhBX/image.png">](https://i.ibb.co/xXymhBX/image.png)

---

## Simple Routing Policy (1/6)
* Maps a hostname to a single resource
* You can't attach health checks to simple routing policy
* If multiple values are returned, a random one is chosen by the <ins>client</ins>

### Diagram
[<img src="https://i.ibb.co/XkTQbR8/image.png">](https://i.ibb.co/XkTQbR8/image.png)

---

## Weighted Routing Policy (2/6)
* Control the % of the requests that go to specific endpoint
* Helpful to **test** 1% of traffic on new app version ofr example
* Helpful to split traffic between two regions - **Load Balancing**
* Can be associated with Health Checks
* Note: The weights don't need to sum up to 100

### Diagram
[<img src="https://i.ibb.co/yR9g7Tp/image.png">](https://i.ibb.co/yR9g7Tp/image.png)

---

## Failover Routing Policy Active - Passive (3/6)
[<img src="https://i.ibb.co/pnRf5MQ/image.png">](https://i.ibb.co/pnRf5MQ/image.png)

---

## Latency Routing Policy (4/6)
* Redirect to the server that has the least latency close to use
* Super hepful when latency of users is a priority
* Latency is evaluated in terms of user to designated AWS Region
* Germany users may be directed to the US (if that's the lowest latency)
* Has failover capability if you enable health checks

### Diagram
[<img src="https://i.imgur.com/fhBrXy0.png">](https://i.imgur.com/fhBrXy0.png)

---

## Geo Location Routing Policy (5/6)
* Different from Laency based!
* This is routing based on user location
* Here we specify: traffic from the UK should go to this specific IP
* Should create a "default" policy (in case there's no match on location)

### Diagram
[<img src="https://i.imgur.com/99HiWHm.png">](https://i.imgur.com/99HiWHm.png)

---

## Multi Value Routing Policy (6/6)
* Use when routing trafic to multiple resources
* Want to assocaite a Route 53 health checks with records
* Up to 8 healthy records are returned for each Multi Value query
* **Multi value** is not a substitute for having an ELB


| Name            | Type     | Value        | TTL | Set ID | Health Check |
|-----------------|----------|--------------|-----|--------|--------------|
| www.example.com | A Record | 192.0.2.2    | 60  | Web1   | A            |
| www.example.com | A Record | 198.51.100.2 | 60  | Web2   | B            |
| www.example.com | A Record | 203.0.113.2  | 60  | Web3   | C            |

---

## Route 53 - Complex/Nested Records
[<img src="https://i.imgur.com/Ifrevfr.png">](https://i.imgur.com/Ifrevfr.png)


---

## Good to know
* Private DNS:
  * Can use Route 53 for internal private DNS
  * Must enable the VPC settings enableDnsHostNames & enableDnsSupport
* **DNSSEC** (protect against MITMA)
  * Route 53 supports DNSSEC for domain registration
  * Route 53 does not support DNSSEC for DNS service
  * To configure DNSSEC for a Route 53 domain, use another DNS provider or custom DNS server on EC2 (Bind, dnsmasq, KnotDNS,PowerDNS)
* 3<sup>rd</sup> party registrar:
  * You can buy the domain out of AWS & use Route 53 as your DNS provider
  * Update the NS records on the 3<sup>rd</sup> party registrar
  
---

## Health Checks with Route 53
* Health Check => automated DNS failovers:
  1) Health checks that monitor an endpoint (application, server, other AWS resource)
  2) Health checks that monitor other health checks (calculated health checks)
  3) Health checks that monitor CloudWatch alarms (full controll!!) - e.g. throttles of DynamoDB, alarms on RDS, custom metrics, etc
* <ins>Health Checks are integrated witch CW metrics</ins>

### Diagram
[<img src="https://i.imgur.com/q1t72Kn.png">](https://i.imgur.com/q1t72Kn.png)

---

## Route 53 Health Checks - good to know
* Health Checks can be setup to pass/fail based on text in the first **5120 bytes** of the response
* Heal Checks pass only with the **2xx** & **3xx** status response
* Calculated health checks
  * Create separate individual health checks 
  * Specify how many of the health checks need to pass to make the parent pass
* Health Checks can trigger CW Alarms

### Diagram
[<img src="https://i.imgur.com/xeeDCxX.png">](https://i.imgur.com/xeeDCxX.png)

---

## Health Checks - Private Hosted Zones
* Route 53 health checkers are outside the VPC
* They can't access **private** endpoints (private VPC or on-premise resource)
* Options:
  * To check a resource within a VPC, you must assign a public IP address
  * You can configure the health checker to check the health of an external resource the instance relies on, for example a database server
* You can create a **CW metric** & associate an alarm. You then create a health check that checks the alarm itself

### Diagram
[<img src="https://i.imgur.com/TqNvRKh.png">](https://i.imgur.com/TqNvRKh.png)

---

## Health Checks Solution Architecture RDS multi-region failover
[<img src="https://i.imgur.com/IrhAFlN.png">](https://i.imgur.com/IrhAFlN.png)

---

## Sharing a Private Zone across VPC
* Having a central private "Shared Services" DNS can ease management
* Other accounts may want to access the central private DNS records
  1) Connectivity between VPC must be established (**VPC peering**)
  2) must programmatically (**CLI**) associate the VPC with the central hosted zone
* One association must be created for each new account

### Diagram
[<img src="https://i.imgur.com/0siTBwb.png">](https://i.imgur.com/0siTBwb.png)
