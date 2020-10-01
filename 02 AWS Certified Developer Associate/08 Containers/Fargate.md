# Fargate

## Acronym
* ECS - Elastic Container Service
* SG - Security group
* ALB - Application Load  Balancer
* LB - Load balancing
* TG - Target Group

## Doc

## Intro
* When lauching an ECS Cluster, we have to create our EC2 instances
* If we need to scale, we need to add EC2 instances
* So we manage infrastructure...
* With Fargate, it's all Serverless!
* We don't provision EC2 instances
* We just create task definitions, & AWS will run our containers for us
* To scale, just increase the task number. Simple! No more EC2 ;-)

---

## Demo
* Create Cluster\Fargate:

[<img src="https://i.imgur.com/e7i5Njj.png">](https://i.imgur.com/e7i5Njj.png)

* cfg cluster
    * cluster name: demo-fargate
    
[<img src="https://i.imgur.com/w4VZUYM.png">](https://i.imgur.com/w4VZUYM.png)

* create services\cfg service
    * launch type: fargate

[<img src="https://i.imgur.com/qTWOd7x.png">](https://i.imgur.com/qTWOd7x.png)

* new task definition
    * launch type : fargate
    * task def. name: fargate-task-definition-demo
    * Task memory (GB): 0.5GB
    * Task CPU: 0.25 vCPU
    * Add container\
        * name httpd
        * image: uri (from ECR\repositories))
        * Memory limits (Mib): hard limit = 512
        * port mappings: 80
        
[<img src="https://i.imgur.com/2VqsasO.png">](https://i.imgur.com/2VqsasO.png)

* cfg service
    * launch type: fargate
    * service name: httpd
    * number of tasks: 2
    * minumum healthy percent: 0
    
* cfg network
    * cluster vpc: default
    * subnets: 3x subnets
    * SG: ALL-ECS-ALB-IN
    
* Load balancing: ALB
* LB name: ECS-HTTPD-ALB
* Add to load balancer
    * Production listener port*: 80:HTTP
    * TG name\create new: ecs-demo-fargate-httpd
    
* tweak, delete old rule with path is / (ALB\listener\rule)

[<img src="https://i.imgur.com/qZsWqhk.png">](https://i.imgur.com/qZsWqhk.png)
[<img src="https://i.imgur.com/izbaaX4.png">](https://i.imgur.com/izbaaX4.png)
