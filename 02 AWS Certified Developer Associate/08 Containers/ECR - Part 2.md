# ECR - Part 2

## Acronym
* ECR - Elastic Container Registry
* TG - Targe Groups
* ALB - Application Load Balancer

## Doc

## Intro
* ECR\repository\our image:

[<img src="https://i.imgur.com/qbxS4t4.png">](https://i.imgur.com/qbxS4t4.png)

* update new Task Definition:

[<img src="https://i.imgur.com/SoZXGSU.png">](https://i.imgur.com/SoZXGSU.png)

* conainer\image\ECR_URI:

[<img src="https://i.imgur.com/ymVMzCl.png">](https://i.imgur.com/ymVMzCl.png)

* third revion of our task definition:

[<img src="https://i.imgur.com/A9dxRFQ.png">](https://i.imgur.com/A9dxRFQ.png)

* update : ECS\service\httpd-alb:

[<img src="https://i.imgur.com/8IWwPUh.png">](https://i.imgur.com/8IWwPUh.png)

* service\task (mixed tag with 2-3):

[<img src="https://i.imgur.com/xpaCqpa.png">](https://i.imgur.com/xpaCqpa.png)

* need to wait to revison 2 down:
* backgroud ELB\TG draining:

[<img src="https://i.imgur.com/3xg97cJ.png">](https://i.imgur.com/3xg97cJ.png)

* check up EC2 (nothing in there):

[<img src="https://i.imgur.com/qbRp8Rk.png">](https://i.imgur.com/qbRp8Rk.png)

* TGs only 2:

[<img src="https://i.imgur.com/Q3Rv4FK.png">](https://i.imgur.com/Q3Rv4FK.png)

* after ~5min draining:
* only httpd:3

[<img src="https://i.imgur.com/lSDYbiO.png">](https://i.imgur.com/lSDYbiO.png)
[<img src="https://i.imgur.com/d2zhqxD.png">](https://i.imgur.com/d2zhqxD.png)

* Browser:

[<img src="https://i.imgur.com/eCWxFV0.png">](https://i.imgur.com/eCWxFV0.png)

* EC2\IAM Role\policy summary:
````text
CloudWatch Logs | write
EC2 | read
Elastic Container Registry | read
Elastic Container Service | write
````

[<img src="https://i.imgur.com/OFxE3S9.png">](https://i.imgur.com/OFxE3S9.png)
[<img src="https://i.imgur.com/r5PD5bL.png">](https://i.imgur.com/r5PD5bL.png)
