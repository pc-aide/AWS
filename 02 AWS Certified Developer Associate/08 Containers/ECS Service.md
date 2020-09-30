# ECS Service

## Doc

## Acronym
* ECS - Elastic Container Service
* ALB - Application Load Balancer
* NLB - Network Load Balancer

## Intro
* ECS Services help define **how many tasks should run** & how they should be run
* They ensure that the number of tasks desired is running across our fleet of EC2 instances
* They can be linked to NLB / ALB if needed

---

## Demo
* First task definition:

[<img src="https://i.imgur.com/LjHyqYP.png">](https://i.imgur.com/LjHyqYP.png)

* Clusters\Create services:
    * Cfg service:
        * Launch type: EC2
        * Task defintion: httpd
        * Service name: httpd-service
        * Service type: REPLICA
        * Number of tasks: 1
        * Minimum healthy percent: 0 (allow us basically to do rolling restarts)
        
[<img src="https://i.imgur.com/TI8lWSZ.png">](https://i.imgur.com/TI8lWSZ.png)

* Deployment:
    * Deployment type: Rolling update
    
* Task Placement:
    * Placement Templates: AZ Balanced Spread
* Next

[<img src="https://i.imgur.com/ditBDe3.png">](https://i.imgur.com/ditBDe3.png)

* Load balancing: none
* Service discovery (optional): disabled
* Next

[<img src="https://i.imgur.com/80mAmO4.png">](https://i.imgur.com/80mAmO4.png)

* Set Auto Scaling: Do not adjust the service's desired count
* Next
* Review
* Create service

[<img src="https://i.imgur.com/WeAl6ub.png">](https://i.imgur.com/WeAl6ub.png)

* Tasks (pending):

[<img src="https://i.imgur.com/MtCPzKE.png">](https://i.imgur.com/MtCPzKE.png)
[<img src="https://i.imgur.com/Jy1s185.png">](https://i.imgur.com/Jy1s185.png)

* Cluster:

[<img src="https://i.imgur.com/MERnhp4.png">](https://i.imgur.com/MERnhp4.png)

* Container instance:

[<img src="https://i.imgur.com/bGrtKZp.png">](https://i.imgur.com/bGrtKZp.png)

* Add 8080 to our SG:

[<img src="https://i.imgur.com/BWBTcUy.png">](https://i.imgur.com/BWBTcUy.png)

* Browser:

[<img src="https://i.imgur.com/2hI7PiV.png">](https://i.imgur.com/2hI7PiV.png)
