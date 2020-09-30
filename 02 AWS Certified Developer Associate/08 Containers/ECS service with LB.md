# ECS service with LB

## Acronym
* LB - Load Balancer
* ECS - Elastic Container Service
* ALB - Application Load Balancer

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

* EC2_01\2x_docker:

[<img src="https://i.imgur.com/hddOBHD.png">](https://i.imgur.com/hddOBHD.png)
