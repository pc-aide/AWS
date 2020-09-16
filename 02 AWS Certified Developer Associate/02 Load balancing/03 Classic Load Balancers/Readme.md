# Classic Load Balancers

## Doc
* [What is a Classic Load Balancer?](https://docs.aws.amazon.com/elasticloadbalancing/latest/classic/introduction.html)

## Acronym
* CLB - Classic Load Balancer
* VH - Virtual Host
* SG - Security Group

## Overview
* Support TCP (Layer 4), HTTP & HTTPS (Layer 7)
* Health checks are TCP or HTTP based
* Fixed hostname
    * xxx.region.elb.amazonaws.com
    
[<img src="https://i.imgur.com/3p9BafJ.png">](https://i.imgur.com/3p9BafJ.png)

## Create an new CLB
* 2x VH on Port 80,443 :

[<img src="https://i.imgur.com/D5bhGdD.png">](https://i.imgur.com/D5bhGdD.png)

* SG Inbound :

[<img src="https://i.imgur.com/48zoCUi.png">](https://i.imgur.com/48zoCUi.png)

* Create Classic LB :

[<img src="https://i.imgur.com/GS95mHi.png">](https://i.imgur.com/GS95mHi.png)

* Step 1 - Define LB :

[<img src="https://i.imgur.com/oJxQk5A.png">](https://i.imgur.com/oJxQk5A.png)

* Step 2 - Assign SG :

[<img src="https://i.imgur.com/AMaaZ7G.png">](https://i.imgur.com/AMaaZ7G.png)

* Step 4 - Configure Health Check :

[<img src="https://i.imgur.com/bqJJLXP.png">](https://i.imgur.com/bqJJLXP.png)

* Step 5 - Add EC2 :

[<img src="https://i.imgur.com/9TWbwew.png">](https://i.imgur.com/9TWbwew.png)

* Overview : 
   * if your status is "out of service" so re-check your SG & after remove & add the EC2 instance again
   
[<img src="https://i.imgur.com/T6hxcO4.png">](https://i.imgur.com/T6hxcO4.png)

* DNS name, if your status is [InService](https://i.imgur.com/nzvimSp.png) so we can check with DNS name :

[<img src="https://i.imgur.com/ds1QPT9.png">](https://i.imgur.com/ds1QPT9.png)
[<img src="https://i.imgur.com/mtmx5Fg.png">](https://i.imgur.com/mtmx5Fg.png)

* it won't woking on port 443, because it's not configured
