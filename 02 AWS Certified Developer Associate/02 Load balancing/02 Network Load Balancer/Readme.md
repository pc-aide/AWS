# 02 Network Load Balancer

## Acronym
* NLB - Network Load Balancer
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

## Topology
[<img src="https://i.imgur.com/iPVfsYD.png">](https://i.imgur.com/iPVfsYD.png)

    
## Test latency (ALB vs NLB)
* New code (more complex) for our index.html on port 80
* NLB - respond (GET) 96.32 ms
* ALB - respond (GET) 120.44 ms

[<img src="https://i.imgur.com/OSAidHX.png">](https://i.imgur.com/OSAidHX.png)
[<img src="https://i.imgur.com/KEs1kpQ.png">](https://i.imgur.com/KEs1kpQ.png)
[<img src="https://i.imgur.com/NzXDTF0.png">](https://i.imgur.com/NzXDTF0.png)
