# X-Ray

## Acronym
* ECS - Elastic Container Service
* IAM - Identity & Access Management

## Visual analysis of our applications
[<img src="https://i.imgur.com/XzIzO0d.png">](https://i.imgur.com/XzIzO0d.png)

---

## Intro
* Tracing request across your microservices (distributed systems)
* Integrations with:
  * EC2 - install the X-Ray agent
  * ECS - install the X-Ray agent or Docker container
  * Lambda
  * Beanstalk - agent is automatically installed
  * API Gateway - helpful to debug error (such as 504: Timeouts)
  * The X-Ray agent or services need IAM permissions to X-Ray
