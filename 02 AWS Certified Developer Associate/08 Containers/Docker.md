# Docker

## Acronym
* ECR - Elastic Container Registry
* VM - Virtual machine
* ECS - Elastic Container Service
* EKS - Elastic Kubernetes Service 

## Doc

## Intro
* Docker is a software development platform to deploy apps
* Apps are packaged in **containers** that can e run on any OS
* Apps run the same, regardless of where they're run
    * Any machine
    * No compatibility issues
    * Predictable behavior
    * Less work
    * Easier to maintain & deploy
    * Works with any language, any OS, any technology
    
---

## Docker on an OS
[<img src="https://i.imgur.com/TYMCR8F.png">](https://i.imgur.com/TYMCR8F.png)

---

## Where Docker images are stored?
* Docker images are stored in Docker Repositories
* Public: Docker Hub: https://hub.docker.com (need a sing in)
    * Find base images for many technologies or OS:
        * Ubuntu
        * MySQL
        * NodeJS, Java...
* Private: Amazon ECR 

---

## Demo
* Search MysQL, Java, Ubuntu, etc:

[<img src="https://i.imgur.com/gplU4H0.png">](https://i.imgur.com/gplU4H0.png)
[<img src="https://i.imgur.com/UDj8hQb.png">](https://i.imgur.com/UDj8hQb.png)
[<img src="https://i.imgur.com/lMPgzJs.png">](https://i.imgur.com/lMPgzJs.png)

---

## Docker vs VM
* Docker is "sort of" a virtualization technology, but not exactly
* Resources are shared with the host => many containers on one server

[<img src="https://i.imgur.com/Qe6xKnx.png">](https://i.imgur.com/Qe6xKnx.png)

---

## Getting Started with Docker
* Download Docker at: https:www.docker.com/get-started

[<img src="https://i.imgur.com/UMuvECG.png">](https://i.imgur.com/UMuvECG.png)
[<img src="https://i.imgur.com/w3er1zv.png">](https://i.imgur.com/w3er1zv.png)

---

## Docker Containers Management
* To manage containers, we need a container managment platform
* Three choices:
    1) ECS
    2) Fargate: Amazon's own Serverless platform
    3) EKS: Amazon's managed Kubernetes (open source)
