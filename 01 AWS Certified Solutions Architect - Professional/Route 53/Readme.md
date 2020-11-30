# Route 53

## Acronym
* Domain Name System
* CLB - Classic Load Balancer
* ALB - Application Load Balancer
* NLB - Network Load Balancer
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
* Redirect to the server that has th
