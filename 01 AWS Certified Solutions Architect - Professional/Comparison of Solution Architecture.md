# Comparison of Solution Architecture

## Acronym
* EIP - Elastic IP
* TTL - Time To Live
* ALB - Application Load Balancer
* ASG - Auto Scaling Group
* AMI - Amazon Machine Image
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
* Adding an instance may not receive full traffic right away due to DNS TTL

### Diagram
[<img src="https://i.imgur.com/Xq0E8WZ.png">](https://i.imgur.com/Xq0E8WZ.png)

---

## ALB + ASG
* Scales well, classic architecture
* New instances are in service right away
* Users are not sent to instances that are out-of-service
* Time to scale is slow (EC2 instance startup + bootstrap) - AMI can help
* ALB is elastic but can't handle sudden, huge peak of demand (pre-warm)
* Could lose a few requests if instances are overloaded
* CloudWatch used for scaling
* Cross-Zone balancing for even traffic distribution
* Target utilization should be between 40% & 70%

### Diagram
[<img src="https://i.imgur.com/UbdDHa8.png">](https://i.imgur.com/UbdDHa8.png)

---

## ALB + ECS on EC2 (backed by ASG)
* Same properties as ALB + ASG
* Application is run on Docker
* ASG + ECS allows to have **dynamic port mappings**
* Tough to orchestrate ECS service auto-scaling + ASG auto-scaling

### Diagram
[<img src="https://i.imgur.com/f7LwxRL.png">](https://i.imgur.com/f7LwxRL.png)

---

## ALB + ECS on Fargate
* Application is run on Docker
* Service Auto Scaling is easy
* Time to be in-service is quick (no need to launch an EC2 instance in advance)
* Still limited by the ALB in case 

### Diagram
