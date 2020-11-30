# ELB

## Acronym
* ELB - Elastic Load Balancer
* L - Layer
* AZ - Availability Zone
* EIP - Elastic IP
* SAN - Subject Alternate Name
* ASG - Auto Scaling Group
* LB - Load Balancer
* SSL - Secure Sockets Layer
* ECS - Elastic Container Service
* SNI - Server Name Indication
* CLB - Classic Load Balancer
* Cert - Certificate
* ALB - Application Load Balancer
* NLB - Network Load Balancer

## Type of LB
* AWS has **3 kinds** of managed LBs
1) CLB (v1 - old generation) - 2009
  * HTTP, HTTPS, TCP
2) ALB (v2 - new generation) - 2016
  * HTTP, HTTPS, WebSocket
3) NLB (v2 - new generation) - 2017
  * TCP, TLS (secure TCP) & UDP
* Overall, it's recommended to use the newer / v2 generation LBs as they provide more features
* You can setup **internal (private)** or **external (public)** ELBs

---

## CLB (v1) Listeners
* Health Checks can be HTTP(L7) or TCP(L4) based
* Supports only one SSL cert
  * The SSL cert can have many SAN, but the SSL cert must be changed anytime a SAN is added/edit/removed
  * Better to use ALB with SNI if possible
  * Can use multiple CLB if you want distinct SSL certificates
* TCP => TCP passes all the traffic to the EC2 instance
  * Only way to use 2-way SSL authentication

* SSL:

| Listener                                                  | Internal                                 |
| --------------------------------------------------------- | ---------------------------------------- |
| HTTP (L7)                                                 | HTTP<br>HTTPS (must install cert on EC2) |
| HTTPS (L7)<br>SSL termination<br>Must install cert on CLB | HTTP<br>HTTPS (must install cert on EC2) |
| TCP (L4)                                                  | TCP<br>SSL (must install cert on EC2)    |
| SSL secure TCP (L4)<br>Must install cert on CLB           | TCP<br>SSL (must install cert on EC2)    |

## Diagram
[<img src="https://i.imgur.com/tVdJjn3.png">](https://i.imgur.com/tVdJjn3.png)

---

## ALB (v2)
* Application LBs is Layer 7 (HTTP)
* Load balancing to multiple HTTP applications across machines (target groups)
* Load balancing to multiple applications on the same machine (ex: containers)
* Support for HTTP/2 & WebSocket
* Support redirects (from HTTP to HTTPS for example)
* Routing tables to different target groups:
  * Rouing based on path in URL (example.com**/user &** example.com/**ports**)
  * Routing based on hostname in URL (**one.example** & **other.example.com**)
  * Routing based on Query String, Headers
    * (example.com/user?**id=123&order=false**)
* ALB are a great fit for micro services & container-based application (example: Docker & ECS)
* Has a port mapping feature to redirect o a dynamic port in ECS
* In camparison, we'd need multiple CLB per application
* Target Groups:
  * EC2 instances (can be managed by an ASG) - HTTP
  * ECS task (managed by ECS itself) - HTTP
  * Lambda functions - HTTP request is translated into a JSON event
  * IP Addresses - must be private IPs (ex: instances in peered VPC, on-premise)
  * ALB can route to multiple target groups
* SSL certificates:
  * Supports multiple listeners
  * Supports SNI 

### HTTP Based Traffic
[<img src="https://i.imgur.com/LrndUfU.png">](https://i.imgur.com/LrndUfU.png)

---

## NLB (v2)
* NLB (Layer 4) allow to do:
  * Forwarded TCP traffic to your instances (**UDP support** - Jun 2019)
  * **handle millions of request per seconds**
  * **NLB has <ins>one static IP per AZ</in>, & supports EIP** (helpful for whitelisting specific IP)
  * Less latency ~100ms (vs 400 ms for ALB)
  * Support for TLS
  * Support for WebSockets
* NLBs are mostly used:
  * for extreme performce, TCP or UDP traffic
  * with AWS Private Link to expose a service internally
* Target Groups:
  * EC2 instances (can be managed by an ASG) - TCP
  * ECS tasks (managed by ECS itself) - TCP
  * IP addresses - Private IP only, even outside your VPC
* Proxy Protocol:
  * Send additional connection information such as the source & destination
  * The LB prepends a proxy protocol header to the TCP data
  * Helpful when you have the "IP addresses" target group type
    * You can retrieve the source IP address of the originating client

---

## Cross-Zone Load Balancing
* With Cross Zone Load Balancing:
  * Each LB instance distributes evenly across all registered instances in all AZ
* Otherwise, each LB node distributes requests evely across the registered instances in its AZ only
* CLB:
  * Disabed by default
  * No charges for inter AZ data if enabled
* ALB:
  * Always on (can't be disabled)
  * No charge for inter AZ data
* NLB:
  * Disabled by default
  * You pay charges ($) for inter AZ data if enabled
  
### Diagram
[<img src="https://i.imgur.com/XhCjpfx.png">](https://i.imgur.com/XhCjpfx.png)

---

## LB Stickiness
* It's possible to implement stickiness so that the same client is always redirected to the same instance behind a LB
* This works for CLB & ALB
* The "cookie" used for stickiness has an expiration data you control
* Use case: make sure the user doesn't lose his session data
* Enabling stickiness may bring imbalance to the load over the backend EC2 instances
* Alternative is to cache session data in ElastiCache, DynamoDB for example

### Diagram
[<img src="https://i.imgur.com/v6ICAAH.png">](https://i.imgur.com/v6ICAAH.png)
