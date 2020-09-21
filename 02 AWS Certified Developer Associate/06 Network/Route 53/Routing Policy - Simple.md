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


* Broswer:

[<img src="https://i.imgur.com/71jKdIS.png">](https://i.imgur.com/71jKdIS.png)
[<img src="https://i.imgur.com/NCpqmVk.png">](https://i.imgur.com/NCpqmVk.png)
