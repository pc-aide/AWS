# ECS Task Definition

## Acronym
* ECS - Elastic Container Service

## Doc

## Intro
* Tasks definitions are metadata in **json form** to tell ECS how to run a Docker Container
* It contains crucial information around:
    * Image Name
    * Port Binding for Container & Host
    * Memory & CPU required
    * Environment variables
    * Networking information
    * and so on
    
### Diagram
[<img src="https://i.imgur.com/5CGGLF7.png">](https://i.imgur.com/5CGGLF7.png)

---

## Demo
* ECS\Task Definitions\Create Task Definition:

[<img src="https://i.imgur.com/Lan7Aun.png">](https://i.imgur.com/Lan7Aun.png)

* Select launch type comp.: EC2
* Cfg task:
    * Task Definition Name: httpd
    * **Task Role**: None
    * Network Mode: Default
    * Task memory (MiB): 300 [(check your RAM available)](https://i.imgur.com/UPkCCKD.png)
    * Task CPU (unit): 250
    * Add container:
        * Conainer name: httpd
        * Image (check up hub.docker.com): httpd:2.4
        * Memory Limits (MiB): 300
        * Port mappings: 8080 (Host port) & 80 (Container port)
        * Add
        * Create
    
[<img src="https://i.imgur.com/WYBy1hk.png">](https://i.imgur.com/WYBy1hk.png)
[<img src="https://i.imgur.com/RoXaDbe.png">](https://i.imgur.com/RoXaDbe.png)
[<img src="https://i.imgur.com/ezRFgvr.png">](https://i.imgur.com/ezRFgvr.png)
[<img src="https://i.imgur.com/d4AOwuS.png">](https://i.imgur.com/d4AOwuS.png)

* First Task Definition:

[<img src="https://i.imgur.com/SlV8qpr.png">](https://i.imgur.com/SlV8qpr.png)

* json:

[<img src="https://i.imgur.com/Kufl0A0.png">](https://i.imgur.com/Kufl0A0.png)
