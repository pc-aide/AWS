# CodeDeploy

## Acronym
* ASG - Auto Scaling Group
* ALB - Application Load Balancer
* CW - CloudWatch
* CI/CD - Continuous Integration/Continuous Delivery
* ECS - Elastic Container Service
* ELB - Elastic Load Balancer
* SAM - Serverless Application Model

## Intro
* We want to deploy our application automatically to many EC2 instances
* These instances are not managed by Elastic Beanstalk
* There are several ways to handle deployments using open source tools (Ansible, Terraform, Chef, Puppet, etc...)
* We can use the managed Service AWS CodeDeploy
* CodeDeploy can deploy to:
  * **EC2**
  * **ASG**
  * **ECS**
  * **Lambda**

### Diagram
[<img src="https://i.imgur.com/Rg5jnD9.png">](https://i.imgur.com/Rg5jnD9.png)

---

## CodeDeploy to EC2
* Define how to deploy the application using **appspec.yml** + deployment strategy
* Will do in-plance update to your fleet of EC2 instances
* Can use **hooks** to verify the deployment after each deployment phase

### Diagram
[<img src="https://i.imgur.com/pZCKbVL.png">](https://i.imgur.com/pZCKbVL.png)

---

## CodeDeploy to ASG
1) In places updates:
  * Updates current existing EC2 instances
  * Instances newly created by an ASG will also get automated deployments
2) Blue/green deployment:
  * Blue - old ver
  * green - new ver
  * A new ASG is created (settings are copied)
  * Choose how long to keep the old instances
  * Must be using an ELB
  
### Diagram
* V1 (90%) & V2 (10%):

[<img src="https://i.imgur.com/KukxK3Z.png">](https://i.imgur.com/KukxK3Z.png)

* V2 (100%):

[<img src="https://i.imgur.com/fkDwZa8.png">](https://i.imgur.com/fkDwZa8.png)

---

## CodeDeploy to Lambda
* **Traffic Shifting** feature
* **Pre & Post traffic hooks**
  * features to validate deployment (before the traffic shift starts & after it ends)
* Easy & automated rollback using CW Alarms
* SAM framework natively uses CodeDeploy

### Diagram
* V1 & V2:

[<img src="https://i.imgur.com/mllTUVk.png">](https://i.imgur.com/mllTUVk.png)

* V2: 

[<img src="https://i.imgur.com/JTR1JrT.png">](https://i.imgur.com/JTR1JrT.png)

---

## CodeDeploy to ECS
* Support for Blue/Green deployments for ECS & Fargate
* Setup is done within the ECS service definition
* A new task is created, & traffic is re-routed to the new task test
* Then is everything is stable for X minutes, the old task set is terminated (so you have time to notice issues)

### Diagram
* Task def v1 (old ver - blue) & task def v2 (new ver - green):

[<img src="https://i.imgur.com/3BvzVQV.png">](https://i.imgur.com/3BvzVQV.png)


* task def v2 (new ver - green):

[<img src="https://i.imgur.com/LNwNAcZ.png">](https://i.imgur.com/LNwNAcZ.png)
