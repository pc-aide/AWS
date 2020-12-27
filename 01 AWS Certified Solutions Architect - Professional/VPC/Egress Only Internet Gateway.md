# Egress Only Internet Gateway

## Abbreviation
* eigw - egress internet gateway
  * only allow out traffic, not in traffic (e.g start session: denied)
* rtb - route tables
* igw - internet gateway

## Intro
* IPv6
  * Unicast address
    * e.g. 2001:ef8:7890:11aa::123
    
* rtb

|Destination            |Target|
|-----------------------|------|
|10.0.0.0/16            |local |
|2001:ef8:7890:11aa::/56|local |
|::/0                   |igw-id|

### Diagram
[<img src="https://i.imgur.com/Ic7FOyx.png">](https://i.imgur.com/Ic7FOyx.png)

