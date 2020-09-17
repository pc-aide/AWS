# ELB - Cross Zone Load Balancing

## Acronym
* ELB - Elastic Load Balancer
* CLB - Classic Load Balancer
* LB - Load Balancer
* AZ - Availability zone
* NLB - Network Load Balancer

## Terminology
* TCP - level 4 (transport)
* HTTP - level 7 (application)
* 304 Not Modified
    * The HTTP 304 Not Modified client redirection response code indicates that there is no need to retransmit the requested resources

[<img src="https://i.imgur.com/o6gzlj2.png">](https://i.imgur.com/o6gzlj2.png)
[<img src="https://i.imgur.com/S71C8dG.png">](https://i.imgur.com/S71C8dG.png)

## Doc
* [cfg cross-zone LB for your CLB](https://docs.aws.amazon.com/elasticloadbalancing/latest/classic/enable-disable-crosszone-lb.html?icmpid=docs_elb_console)
* [What is a CLB?](https://docs.aws.amazon.com/elasticloadbalancing/latest/classic/enable-disable-crosszone-lb.html?icmpid=docs_elb_console)

## Introduction
* With Cross Zone Load Balaancing: each LB instance distribures evenly across all registered instances in all AZ
* Otherwise, each LB node distributes requests evenly across the registered instances in its AZ only


### Topology
[<img src="https://i.imgur.com/Vh66Qn9.png">](https://i.imgur.com/Vh66Qn9.png)

## Cross Zone LB
### CLB
* Default: Disabled - udemy said that (we my new [CLB it's checkbox automatic)](https://i.imgur.com/mYDrn8F.png)
* No charges for inter AZ data if enabled

#### Demo
* 2x EC2 & one DNS

[<img src="https://i.imgur.com/HZOEJ7E.png">](https://i.imgur.com/HZOEJ7E.png)

#### Monitoring
[<img src="https://i.imgur.com/LVRRoRd.png">](https://i.imgur.com/LVRRoRd.png)

### ALB
* Default: Always on (can't be disabled - no option)
* No charges for inter AZ data

#### Demo
* 2x EC2 | 2x AZ

[<img src="https://i.imgur.com/KnajrfC.png">](https://i.imgur.com/KnajrfC.png)
[<img src="https://i.imgur.com/d7yorW4.png">](https://i.imgur.com/d7yorW4.png)

#### Monitoring
[<img src="https://i.imgur.com/128G39F.png">](https://i.imgur.com/128G39F.png)

### NLB
* Disabled by default

#### Demo
[<img src="https://i.imgur.com/jrOBK1t.png">](https://i.imgur.com/jrOBK1t.png)

* Target Group, only one AZ "healthy", the other "unused"

[<img scr="https://i.imgur.com/GXNhf2N.png">](https://i.imgur.com/GXNhf2N.png)

* Don't forget to put another subnet (AZ)

[<img src="https://i.imgur.com/Vl94QSa.png">](https://i.imgur.com/Vl94QSa.png)

* Wainting for health :

[<img src="https://i.imgur.com/JDUKBVl.png">](https://i.imgur.com/JDUKBVl.png)
[<img src="https://i.imgur.com/SpFZKE9.png">](https://i.imgur.com/SpFZKE9.png)

* even after 10x F5, userX still on ec2ama-01 - never on ec2ama-02
* Why versus othr LB ?

[<img src="https://i.imgur.com/iR2XW1l.png">](https://i.imgur.com/iR2XW1l.png)

* If i clear browsing data, so now i'm on the second instance 02

[<img src="https://i.imgur.com/5VMiRo6.png">](https://i.imgur.com/5VMiRo6.png)

* the time + algorithm LB !?

[<img src="https://i.imgur.com/nxOjFVz.png">](https://i.imgur.com/nxOjFVz.png)
[<img src="https://i.imgur.com/6eTKhuo.png">](https://i.imgur.com/6eTKhuo.png)

* Enabled Cross Zone :

[<img src="https://i.imgur.com/qLu9MYF.png">](https://i.imgur.com/qLu9MYF.png)
[<img src="https://i.imgur.com/k6rPSuU.png">](https://i.imgur.com/k6rPSuU.png)

#### Monitoring
[<img src="https://i.imgur.com/Ew6nJI4.png">](https://i.imgur.com/Ew6nJI4.png)

## Overview 3x LB 
[<img src="https://i.imgur.com/fTjVa7D.png">](https://i.imgur.com/fTjVa7D.png)
