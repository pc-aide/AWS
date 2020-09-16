# 02 Load balancing

## Doc

## Acronym
* LB - Load Balancer
* HA - High Availability
* CLB - Classic Load Balancer
* ALB - Application Load Balancer

## What is ?
* Load balancers are servers that forward internet traffic to multiple servers (EC2 Instances) downstream

[<img src="https://i.imgur.com/FaGoVIg.png">](https://i.imgur.com/FaGoVIg.png)

## Why use a loa balancer?
* Spread load across multiple downstream instances
* Expose a single point of acesses (**DNS**) to your application
* Do regular health checks to your instances
* Provide SSL termination (HTTPS) for your websites
* Enforce stickiness with cookies
* HA across zones
* Separate public traffic from private traffic

## Why use an EC2 LB?
* An ELB (EC2 Load Balancer) is a **managed load balancer**
    * AWS guarantees that it will be working
    * AWS takes care of upgrades, maintenance, HA
    * AWS provides only a few configuration knobs
* It costs less to setup your own load balancer but it will be a lot more effort on your end
* It is integrated with many AWS offerings / services

## Health Checks 
* Health Checks are crusial for LBs
* They enable the LB to knwo if instances it forwards traffic to are available to reply to requests
* The health check is done on a port & a route (/health is common)
* If the response is not 200 (OK), then the instance is unhealthy

[<img src="https://i.imgur.com/O7EMFQM.png">](https://i.imgur.com/O7EMFQM.png)

## Types of LB
* AWS has **3 kinds of managed LBs**
* You can setup **internal** (private) or **external** (public) ELBs
* LBs can scale but not instantaneously - contact AWS for a "warm-up"
* Troubleshooting (return HTTP):
    * 4xx errors are **client** induced errors
    * 5xxx errors are **application** induced errors
    * LB errrors 503 means at capacity or no registered target
    * If the LB can't connect to your application, check your security groups!
* Monitoring 
    * ELB access logs will log all access requests (so you can debug per request)
    * CloudWatch Metrics will give you aggregate statistics (ex: connections count)

### Classic LB 
* Classic Load Balancer (v1 - old generation) - 2009
    * HTTP, HTTPS, TCP

### Application LB
* Application Load Balancer (v2 - new generation) - 2016
    * HTTP, HTTPS, WebSocket
    
### Network LB
* Network Load Balancer (v2 - new generation) - 2017
    * TCP, TLS (secure TCP) & UDP
* Overall, it's recommended to use the new / v2 generation LBs as they provide more features

## LB Security Groups

[<img src="https://i.imgur.com/3V6zgOR.png">](https://i.imgur.com/3V6zgOR.png)

## LB Stickiness
* It's possible to implement stickiness so that the same client is always redirected to the same instance behind a LB
* This work for CLB & ALB
* The "cookie" used for stickiness has an expiration data you control
* Use case: make sure the user doesn't lose his session data
* Enabling stickiness may bring imbalance to the load over the backend EC2 instances

### Tolopoly
[<img src="https://i.imgur.com/PxojDpb.png">](https://i.imgur.com/PxojDpb.png)

### Demo
* 2x EC2

[<img src="https://i.imgur.com/0A1LMyF.png">](https://i.imgur.com/0A1LMyF.png)

* SG: 

[<img src="https://i.imgur.com/oF0kTzV.png">](https://i.imgur.com/oF0kTzV.png)

* Target Group:
   * If some issue with unhealthy, so check SG & apache reload for example
   
[<img src="https://i.imgur.com/4ftYCk2.png">](https://i.imgur.com/4ftYCk2.png)

* 2x users different
   * scenario 01
      * User1 -> EC2ama-02
      * User2 -> EC2ama-01

[<img src="https://i.imgur.com/L5ZZ6Hr.png">](https://i.imgur.com/L5ZZ6Hr.png)

* If  the user1 refresh page, so it will get EC2ama-01

[<img src="https://i.imgur.com/WkXPHmv.png">](https://i.imgur.com/WkXPHmv.png)

* Stickiness: Disabled

[<img src="https://i.imgur.com/ZaAA1Qh.png">](https://i.imgur.com/ZaAA1Qh.png)

* Stickiness: Enable (for 120) sec

[<img src="https://i.imgur.com/121DU4N.png">](https://i.imgur.com/121DU4N.png)

* Now user1 (logo cat) = ec2ama-02 even after F5

[<img src="https://i.imgur.com/XpzC5BX.png">](https://i.imgur.com/XpzC5BX.png)

* Same logic for User2 (logo Windows) = ec2ama-01 even after F5
   * if the user2 on ec2ama-02, so just delete the sessionID (cookies)
   
[<img src="https://i.imgur.com/S9vL5lc.png">](https://i.imgur.com/S9vL5lc.png)
