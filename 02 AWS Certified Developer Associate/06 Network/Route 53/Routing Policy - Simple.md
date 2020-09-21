# Routing Policy - Simple

## Doc

## Acronym
* SG - Security Group

## Introduction
* Use when you need to redirect to a single resource
* You can't attach health checks to simple routing policy
* If multiple values are returned, a random one is chosen by the <ins>client</ins>

### Diagram
[<img src="https://i.imgur.com/oFN7v6a.png">](https://i.imgur.com/oFN7v6a.png)

---

## Demo Cross Region
### EC2
* Regions: ca & us
* SG: (for demo - it's not best practice - we want only LB managed traffic - see later)

[<img src="https://i.imgur.com/n3yJ0nN.png">](https://i.imgur.com/n3yJ0nN.png)

### Route 53
* Type: A - IPv4
* value: 
  * IP_Canada
  * IP_US

[<img src="https://i.imgur.com/bS1ic69.png">](https://i.imgur.com/bS1ic69.png)

### Broswer:

[<img src="https://i.imgur.com/71jKdIS.png">](https://i.imgur.com/71jKdIS.png)
[<img src="https://i.imgur.com/NCpqmVk.png">](https://i.imgur.com/NCpqmVk.png)

* we dont' want this (check SG+ Route 53) :

[<img src="https://i.imgur.com/INK3uf7.png">](https://i.imgur.com/INK3uf7.png)

### Info
[<img src="https://i.imgur.com/7EBvGR3.png">](https://i.imgur.com/7EBvGR3.png)
[<img src="https://i.imgur.com/agfuhQR.png">](https://i.imgur.com/agfuhQR.png)

#### Cue
* Good SG (managed only LB - idem for 2x EC2-{ca,us}):

[<img src="https://i.imgur.com/3KS0LUj.png">](https://i.imgur.com/3KS0LUj.png)

* Route 53\record A - we can put many ip but no dns name for example

[<img src="https://i.imgur.com/HczD934.png">](https://i.imgur.com/HczD934.png)

* we want one Domain Name with multiple IPs:

[<img src="https://i.imgur.com/mVfelfb.png">](https://i.imgur.com/mVfelfb.png)

* If we try for example record ip each LB Regions (DNS Name) 
* we can take Root domain - for the demo :

[<img src="https://i.imgur.com/pF24Qd3.png">](https://i.imgur.com/pF24Qd3.png)
[<img src="https://i.imgur.com/cR6yCOP.png">](https://i.imgur.com/cR6yCOP.png)
[<img src="https://i.imgur.com/743kYlz.png">](https://i.imgur.com/743kYlz.png)

* Firsrt problem - we need wait 300 TTL twice (1st & 2nd ip : ca-cetnral before to get us-east):

[<img src="https://i.imgur.com/WAJZc0A.png">](https://i.imgur.com/WAJZc0A.png)

* wait 300 * 2 (TTL) - or cheating we cache browser or flush dns:

[<img src="https://i.imgur.com/sTKEccm.png">](https://i.imgur.com/sTKEccm.png)

* yes can in record : A - alternative ip: ca-us vs 2x ca & 2x us

[<img src="https://i.imgur.com/L1uzHSu.png">](https://i.imgur.com/L1uzHSu.png)
[<img src="https://i.imgur.com/NQzD8bD.png">](https://i.imgur.com/NQzD8bD.png)`

* Much secure - can't passed directly by the IPs:

[<img src="https://i.imgur.com/pB0AdEG.png">](https://i.imgur.com/pB0AdEG.png)
