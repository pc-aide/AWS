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
