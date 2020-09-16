# Application Load Balancer

## Doc
* [What is an Application Load Balancer?](https://docs.aws.amazon.com/elasticloadbalancing/latest/application/introduction.html)

## Acronym
* ALB - Application Load Balancer
* ECS - Elastic Container Service
* XFF - X-Forwarded-For

## Terminology
* Model ISO ( with 7 layers)
* WebScoket
* X-Forwarded-For

## Overview
* Application Load balancers is Layer 7 (HTTP)
* Load balancing to multiple HTTP applications across machines (target groups)
* Load balancing to multiple application on the same machine (ex.: contrainers)
* Support for HTTP/2 & WebSocket
* Routing tables to different target groups
    * Routing based on path in URL (SimpleAppTest.com/**Users** & SimpleAppTest.com/**Blog**)
    * Routing based on hostname in URL (**one.example.com** & **other.example.com**)
    * Routing based on Query String, Headers (example.com/user?**id=123&order=false**)
* ALB are a great fit for micro services & container-based application, ex :  
    * Docker
    * ECS
* Has a port mapping feature to redirect to a dynamic port in ECS
* In comparison, we'd need multiple CLB per application
* Fixed hostname (xxx.region.elb.amazonaws.com)
      * SimpleAppTestALB-593251739.ca-central-1.elb.amazonaws.com
* A new ALB need at least **two subnets** must be specified

[<img src="https://i.imgur.com/Qa9jnkT.png">](https://i.imgur.com/Qa9jnkT.png)

* The application servers don't see the IP of the client directly
      * The true IP of the client is inserted in the header **X-Forearded-for**
      * We can also get Port (X-Forwarded-Port) & proto (X-Forwarded-Proto)
      
[<img src="https://i.imgur.com/O3ioKoB.png">](https://i.imgur.com/O3ioKoB.png)

[<img src="https://i.imgur.com/xZYlTb2.png">](https://i.imgur.com/xZYlTb2.png)

## Target Groups
* EC2 instances (can be managed by an Auto Scaling Group) - HTTP
* ECs tasks (managed by ECS itself) - HTTP
* Lambda functions - HTTP request is translated into a JSON event
* IP adresses - must be private IPs
* ALB can route to multiple target groups
* Health checks are at the target group level

## HTTP header
* No X-Forwarded-For
* Web server apache2
* No container

[<img src="https://i.imgur.com/ZPxeTLl.png">](https://i.imgur.com/ZPxeTLl.png)
[<img src="https://i.imgur.com/NRH9DPh.png">](https://i.imgur.com/NRH9DPh.png)
[<img src="https://i.imgur.com/DZHHttM.png">](https://i.imgur.com/DZHHttM.png)
[<img src="https://i.imgur.com/Qjy5gK7.png">](https://i.imgur.com/Qjy5gK7.png)
[<img src="https://i.imgur.com/3wOH2zU.png">](https://i.imgur.com/3wOH2zU.png)
[<img src="https://i.imgur.com/vMyHcQG.png">](https://i.imgur.com/vMyHcQG.png)

## New ALB
* Waiting for **provisioning** ...
[<img src="https://i.imgur.com/YwdfQS3.png">](https://i.imgur.com/YwdfQS3.png)
