# Beanstalk with Docker.md

## Acronym
* EB - Elastic Beanstalk
* ECS - Elastic Container Service
* LB - Load  Balancer
* HA - High Availability
* ECR - Elastic Container Registry
* SRV - Server
* ASG - Auto-Scaling Group

## Doc

## EB - Single Docker
* Run your application as a single docker container
* Either provide:
    * **DockerFile**: EB will build & run the Docker container
    * **DockerRun.aws.json (v1)**: Describe where *already built* Docker image is
      * Image
      * Ports
      * Volumes
      * Logging
      * Etc...
* Beanstalk in Single Docker Container <ins>does not use ECS</ins>

---

## EB - Multi Docker Container
* Multi Docker helps run multiple containers per EC2 instance in EB
* This will creae for your:
      * ECS Cluster
      * EC2 instances, configured to use the ECS Cluster
      * LB (in HA mode)
      * Task definitions & execution
* Requires a config **Dockerrun.aws.json (v2)** at the root of source code
* **Dockerrun.asws.json** is used to generate the **ECs task defintion**
* Your Docker images must be pre-built & stored in ECR for example

### Diagram
[<img src="https://i.imgur.com/Bg8ALBP.png">](https://i.imgur.com/Bg8ALBP.png)

---

## Demo
* EB\Applications\Demo-Beanstalk:

[<img src="https://i.imgur.com/ebXHMx8.png">](https://i.imgur.com/ebXHMx8.png)

* Create new env\web srv env:
      * Env name: DemoBeanstalk-Docker
      * Platform: Docker
      * Platform branch: Multi-container Docker running on 64bit...
      * Create env
      
[<img src="https://i.imgur.com/mgZawGI.png">](https://i.imgur.com/mgZawGI.png)

* [Sample applications](https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/RelatedResources.html):

[<img src="https://i.imgur.com/3xNPoik.png">](https://i.imgur.com/3xNPoik.png)

* file zip:

[<img src="https://i.imgur.com/waU7rqC.png">](https://i.imgur.com/waU7rqC.png)

* Dockerrun.aws.json:

[<img src="https://i.imgur.com/OCy52Ip.png">](https://i.imgur.com/OCy52Ip.png)
      
* .ebextensions/01-nginx-healthd.config (yaml):

[<img src="https://i.imgur.com/JBJbFEP.png">](https://i.imgur.com/JBJbFEP.png)

* php:

[<img src="https://i.imgur.com/N9WmUi3.png">](https://i.imgur.com/N9WmUi3.png)
[<img src="https://i.imgur.com/Nm4Bc1W.png">](https://i.imgur.com/Nm4Bc1W.png)

* DemoBeanstalk-Docker:

[<img src="https://i.imgur.com/ffMa9tc.png">](https://i.imgur.com/ffMa9tc.png)

* Browser:

[<img src="https://i.imgur.com/Bt78oD8.png">](https://i.imgur.com/Bt78oD8.png)

* ECS:

[<img src="https://i.imgur.com/NwBCgEv.png">](https://i.imgur.com/NwBCgEv.png)
[<img src="https://i.imgur.com/lcgeZNp.png">](https://i.imgur.com/lcgeZNp.png)
[<img src="https://i.imgur.com/SAivn21.png">](https://i.imgur.com/SAivn21.png)
[<img src="https://i.imgur.com/zKdEqQI.png">](https://i.imgur.com/zKdEqQI.png)

* ASG:

[<img src="https://i.imgur.com/lhmIXxF.png">](https://i.imgur.com/lhmIXxF.png)
