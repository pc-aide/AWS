# ECS service with LB

## Acronym
* LB - Load Balancer
* ECS - Elastic Container Service
* ALB - Application Load Balancer
* TG: Target Groups

## Doc

## Intro
* Dynamic port forwarding in ALB to point the right httpd & port (website01, website02, etc)

### Diagram
[<img src="https://i.imgur.com/b3lbaU6.png">](https://i.imgur.com/b3lbaU6.png)

---

## Demo
* Cluster\service\task\update: Number of tasks : 4

[<img src="https://i.imgur.com/bl6EfF8.png">](https://i.imgur.com/bl6EfF8.png)
[<img src="https://i.imgur.com/bJ3ARBb.png">](https://i.imgur.com/bJ3ARBb.png)

* need update task definition (ports):
* Create new revison:

[<img src="https://i.imgur.com/CPjJBuG.png">](https://i.imgur.com/CPjJBuG.png)

* select httpd:
* empty (host port) - empty = random:

[<img src="https://i.imgur.com/hNWOxaV.png">](https://i.imgur.com/hNWOxaV.png)

* create
* task:defintion:version2:

[<img src="https://i.imgur.com/Jtc4Bh3.png">](https://i.imgur.com/Jtc4Bh3.png)
[<img src="https://i.imgur.com/jGUL2b2.png">](https://i.imgur.com/jGUL2b2.png)

* update this new service
* cluster\service\update

[<img src="https://i.imgur.com/Nby2wGZ.png">](https://i.imgur.com/Nby2wGZ.png)
[<img src="https://i.imgur.com/FtyPLSH.png">](https://i.imgur.com/FtyPLSH.png)

* httpd-service\deployments:

[<img src="https://i.imgur.com/npPsOcM.png">](https://i.imgur.com/npPsOcM.png)

* EC2\2x units:

[<img src="https://i.imgur.com/HXzkpy3.png">](https://i.imgur.com/HXzkpy3.png)

*2x_dockers_random_port:

[<img src="https://i.imgur.com/yZVYCcN.png">](https://i.imgur.com/yZVYCcN.png)
[<img src="https://i.imgur.com/XIWlOWm.png">](https://i.imgur.com/XIWlOWm.png)
[<img src="https://i.imgur.com/5psZaB0.png">](https://i.imgur.com/5psZaB0.png)

* cluster\service\events:

[<img src="https://i.imgur.com/GJSJ0YD.png">](https://i.imgur.com/GJSJ0YD.png)

### LB
* Cluster\Create service (with LB):

[<img src="https://i.imgur.com/QE6FHNc.png">](https://i.imgur.com/QE6FHNc.png)

* Cfg service
    * Launch type: EC2
    * Task Definition: httpd (family) | 2 (revision)
    * Service name: httpd-alb
    * Number of tasks: 4
    * Minimum healthy percent: 0
    * Next step
* Load balancing
    * Load balancer type: Application Load Balancer
    * Service IAM role: Create new role
    * Load Balancer name: nothing -need to create one
    
[<img src="https://i.imgur.com/TJD47eN.png">](https://i.imgur.com/TJD47eN.png)

* New SG (EC2):
    * Name: ALL-ECS-ALB-IN
    * Inbound
        * Type: all traffic
        * Source: HTTP-LB-IN

[<img src="https://i.imgur.com/1qoiOi0.png">](https://i.imgur.com/1qoiOi0.png)
[<img src="https://i.imgur.com/Oa7FPBj.png">](https://i.imgur.com/Oa7FPBj.png)
[<img src="https://i.imgur.com/2JkckK2.png">](https://i.imgur.com/2JkckK2.png)

* Container to load balance:
    * Add to load balancer
    
[<img src="https://i.imgur.com/4AlevTS.png">](https://i.imgur.com/4AlevTS.png)
[<img src="https://i.imgur.com/O501H54.png">](https://i.imgur.com/O501H54.png)

* httpd:80
    * Prodection listener port: 80:HTTP
    * Path pattern: /
    * Evaluation order: 1
    * Health check patch: /
* Next
    
[<img src="https://i.imgur.com/cDGLPxw.png">](https://i.imgur.com/cDGLPxw.png)
[<img src="https://i.imgur.com/oY6M4Ln.png">](https://i.imgur.com/oY6M4Ln.png)

* Review:
* Create service:

[<img src="https://i.imgur.com/OT5aSPW.png">](https://i.imgur.com/OT5aSPW.png)
[<img src="https://i.imgur.com/qDESdVv.png">](https://i.imgur.com/qDESdVv.png)

* service:httpd-alb:

[<img src="https://i.imgur.com/T4yAcBL.png">](https://i.imgur.com/T4yAcBL.png)

* 2x service on one cluster:

[<img src="https://i.imgur.com/Zh2e7X7.png">](https://i.imgur.com/Zh2e7X7.png)

* Delete old service (httpd-service) after update desired task=0:

[<img src="https://i.imgur.com/3yZ2mGn.png">](https://i.imgur.com/3yZ2mGn.png)
[<img src="https://i.imgur.com/x0VCQwy.png">](https://i.imgur.com/x0VCQwy.png)

* Test DNS Name (ALB):

[<img src="https://i.imgur.com/fwpE9jx.png">](https://i.imgur.com/fwpE9jx.png)

* ALB:

[<img src="https://i.imgur.com/znvGyzk.png">](https://i.imgur.com/znvGyzk.png)

* TG:

[<img src="https://i.imgur.com/rfKTY11.png">](https://i.imgur.com/rfKTY11.png)
