# Comparison of Solution Architecture

## Acronym
* EIP - Elastic IP
* TTL - Time To Live
* ALB - Application Load Balancer
* ASG - Auto Scaling Group
* DR - Disaster Recovery
* ECS - Elastic Container Service

## Intro
* EC2 on its own with EIP
* EC2 with Route 53
* ALB + ASG
* ALB + ECS on EC2
* ALB + ECS on Fargate
* ALB + Lambda
* ALB Gateway + Lambda
* API Gatewy + AWS Service
* API Gateway + HTTP backend (ex:ALB)

---

## EC2 with EIP
* Quick failover
* The client should not see the change happen
* Helpfull fi the client needs to resolve by static Public IP address
* Does not scale
* Cheap 

### Diagram
[<img src="https://i.imgur.com/uUfsjOK.png">](https://i.imgur.com/uUfsjOK.png)

---

## Stateless web app - scaling horizontally
* "DNS-based load balancing"
* Ability to use multiple instances
* Route 53 TTL implies client may get outdated information
* Clients must have logic to deal with hostname resolution failures
* Adding an 

## Diagram
