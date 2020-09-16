# Application Load Balancer

## Doc
* [What is an Application Load Balancer?](https://docs.aws.amazon.com/elasticloadbalancing/latest/application/introduction.html)

## Acronym
* ALB - Application Load Balancer
* ECS - Elastic Container Service

## Terminology
* Model ISO ( with 7 layers)

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

[<img src="https://i.imgur.com/xZYlTb2.png">](https://i.imgur.com/xZYlTb2.png)
