# 02 Network Load Balancer

## Acronym
* NLB - Network Load Balancer
* SG - Security Group
* VH - Virtual Host
* ALB - Application Load Balancer
* AZ - Availability Zone
* EIP - Elastic IP

## Doc
* [network/introduction](https://docs.aws.amazon.com/elasticloadbalancing/latest/network/introduction.html)

## Overview
* Network load balancers (Layer 4) allow to :
    * Forwarding TCP & UDP traffic to your instances
      * Low level
    * Handle millions of request per seconds 
    * Less latency ~100ms (vs 400 ms for ALB)
* NLB has **one static IP per AZ**, & supports assigning EIP
    * Helpful ofr whitelisting specific IP
* NLB are used for extreme performance, TCP or UDP traffic
* Not included in the AWS free tier
* At least one subnet must be specified (new NLB)

## Provising
* ~ 1min before to active

[<img src="https://i.imgur.com/YrFr032.png">](https://i.imgur.com/YrFr032.png)
[<img src="https://i.imgur.com/XDCGT5r.png">](https://i.imgur.com/XDCGT5r.png)

## Target Group
* If **unhealthy** check your SG for your instance

[<img src="https://i.imgur.com/B029E2k.png">](https://i.imgur.com/B029E2k.png)
[<img src="https://i.imgur.com/MvR8z6P.png">](https://i.imgur.com/MvR8z6P.png)

### Error
* I created my TG first, & when i want to creat a new LB (ALB), it can't see my TG

[<img src="https://i.imgur.com/UzoD3dl.png">](https://i.imgur.com/UzoD3dl.png)

## Security Group
* E.g
   * SGName: HTTP-IN-Any
   * Port: 80
   * Protocol: tcp
   * SRC: 0.0.0.0/0
      
[<img src="https://i.imgur.com/ISBGffs.png">](https://i.imgur.com/ISBGffs.png)

## nslookup

[<img src="https://i.imgur.com/hl0y3mO.png">](https://i.imgur.com/hl0y3mO.png)

## Topology
[<img src="https://i.imgur.com/iPVfsYD.png">](https://i.imgur.com/iPVfsYD.png)

    
## Test latency (ALB vs NLB)
* New code (more complex) for our index.html on port 80
* NLB - respond (GET) 96.32 ms
* ALB - respond (GET) 120.44 ms

[<img src="https://i.imgur.com/OSAidHX.png">](https://i.imgur.com/OSAidHX.png)
[<img src="https://i.imgur.com/KEs1kpQ.png">](https://i.imgur.com/KEs1kpQ.png)
[<img src="https://i.imgur.com/NzXDTF0.png">](https://i.imgur.com/NzXDTF0.png)

### Timing
* ALB vs NLB
     * Same EC2 for my VH

[<img src="https://i.imgur.com/htvU51S.png">](https://i.imgur.com/htvU51S.png)
