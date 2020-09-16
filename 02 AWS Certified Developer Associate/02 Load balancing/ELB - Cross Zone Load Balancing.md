# ELB - Cross Zone Load Balancing

## Acronym
* ELB - Elastic Load Balancer
* CLB - Classic Load Balancer
* LB - Load Balancer
* AZ - Availability zone
* NLB - Network Load Balancer

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

### ALB
* Default: Always on (can't be disabled - no option)
* No charges for inter AZ data

#### Demo
* 2x EC2 | 2x AZ

[<img src="https://i.imgur.com/KnajrfC.png">](https://i.imgur.com/KnajrfC.png)
[<img src="https://i.imgur.com/d7yorW4.png">](https://i.imgur.com/d7yorW4.png)

### NLB
* Disabled by default

#### Demo
[<img src="https://i.imgur.com/jrOBK1t.png">](https://i.imgur.com/jrOBK1t.png)
