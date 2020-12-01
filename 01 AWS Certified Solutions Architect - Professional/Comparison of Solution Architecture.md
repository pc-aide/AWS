# Comparison of Solution Architecture

## Acronym
* EIP - Elastic IP
* SQS - Simple Queue Service
* WAF - Web Application Firewall
* LB - Load Balancer
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
* Still limited by the ALB in case of sudden peaks
* "Serverless" application tier
* "Managed" LB

### Diagram
[<img src="https://i.imgur.com/W5AVQxx.png">](https://i.imgur.com/W5AVQxx.png)

---

## ALB + Lambda
* Limited to Lambda's runtimes
* Seamless scaling thanks to Lambda
* Simple way to expose Lambda functions as HTTP/S without all the features from API Gateway
* Can combine with WAF
* Good for hybrid microservices
* Example: use ECS for some requests, use Lambda for others

### Diagram
[<img src="https://i.imgur.com/xhQg6V7.png">](https://i.imgur.com/xhQg6V7.png)

---

## API Gateway + Lambda
* Pay per reuest, seamless scaling, fully serverless
* Soft limits: 10k/s API Gateway, 1k concurrent Lambda
* API Gateway features:
  * authentication, rate limiting, caching, etc...
* Lambda Cold Start time may increase latency for some requests
* Fully integrated with X-Ray

### Diagram
[<img src="https://i.imgur.com/aw5xuR2.png">](https://i.imgur.com/aw5xuR2.png)

---

## API Gateway + AWS Service (as a proxy)
* Lower latency, cheaper
* Not using Lambda concurrent capacity, no custom code
* Expose AWS APIs securely through API Gateway
* SQS, SNS, Step Functions...
* Remember API Gateway has a payload limit of 10MB (can be a problem ofr S3 proxy)

### Diagram
[<img src="https://i.imgur.com/hpBp4NH.png">](https://i.imgur.com/hpBp4NH.png)

---

## API Gateway + HTTP backend (ex: ALB)
* Use API Gateway features on top of custom HTTP backend (authentication, rate control, API keys, caching...)
* Can connect to...
* On-premise service
* ALB
* 3<sup>rd</sup> party HTTP service


## Diagram
