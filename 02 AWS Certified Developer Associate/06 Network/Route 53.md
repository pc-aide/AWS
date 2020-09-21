# Route 53

## Acronym
* DNS - Domain Name System
* LB - Load Balancing

## Doc

## Introduction
* Route 53 is a Managed DNS
* DNS is a collection of rules & records which helps clients understand how to reach a server though its domain name
* In AWS, the most common records are:
    * A: hostname to IPv4 
      * rds.ca -> 199.85.71.129
    * AAAA: hostname to IPv6
    * **CNAME**: hostname to hostname
    * Alias: hostname to AWS resource
* Route 53 can use:
    * public domain names you own (or buy)
      * application1.myPublicDomain.com
    * private domain names that can be resolved by our instances in your VPCs
      * Application1.Company.Internal
* Route 53 has advanced features such as:
    * LB (through DNS - also called client LB)
    * Health checks (although limited...)
    * Routing policy: simple, failover, geolocation, latency, weighted, multi value
* You pay 0.5$ per month per hosted zone
    
## Diagram
[<img src="https://i.imgur.com/mF5Wm8w.png">](https://i.imgur.com/mF5Wm8w.png)
