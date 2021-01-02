# NLB

## Acronym
* ALB - Application Load Balancer
* AZ - Availability Zone
* EIP - Elastic IP
* IAM - Identity & Access Management
* LB - Load Balancer
* NLB - Network Load Balancer
* TG - Target Group

## Abbreviation
* cfg - configuration

## Intro
* NLB
  * high performance
* focus networking layer of the traffic as opposed to hte application layer (ALB)

## Create NLB
### 01 - cfg LB
1) Name: <string>
2) Scheme:
  * internet-facing - public
  * internal - private
3) Listeners:
  * Protocol
    * TCP
    * TLS (Secure TCP) - need SSL here
    * UDP
    * TCP_UDP

|n|LB Protocol|LB Port|
|-|-----------|-------|
|1|TCP        | 80    |

4) AZ
  * VPC: default or take one existing
  * AZs: leat one AZ
    * IPv4 address: Assigned by AWS or EIP
  
### 02 - cfg Security Settings
1) cert (if choose TLS) type:
  * Choose a cert from ACM
  * Upload a cert to ACM
  * Choose a cert from IAM
  * Upload a cert to IAM
2) Security Policy
 * ELBSecurityPolicy-2016-08 (default)
  

### 03 - cfg Routing
1) TG: existing or new one
2) Target type:
  * Instance
  * IP
3) Protocol
  * TCP
  * TLS
4) Port
5) Health check
  * Prototol
    * TCP - check network
    * HTTP - check application
    * HTTPS
  * Advanced health check settings (optional)
  
### 04 - Register Targets
1) IP addresses

|Network                   |IP (Allowed ranges|Port|Add to list|
|--------------------------|------------------|----|-----------|
|vpc-26994f4f(172.31.0.0/16|172.31.5.153      | 80 |           |


[<img src="https://i.imgur.com/wFnUQ5m.png">](https://i.imgur.com/wFnUQ5m.png)

* SG here, must to be settup at level EC2 et not at level LB (versus ALB)
* so if website timeout, check up your SG for EC2 for NLB!

--

