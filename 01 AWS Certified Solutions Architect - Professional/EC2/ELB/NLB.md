# NLB

## Acronym
* ALB - Application Load Balancer
* AZ - Availability Zone
* EIP - Elastic IP
* LB - Load Balancer
* NLB - Network Load Balancer

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
  * 
  
li { cursor: pointer; }
