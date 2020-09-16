# ELB - Cross Zone Load Balancing

## Acronym
* ELB - Elastic Load Balancer
* CLB - Classic Load Balancing
* LB - Load Balancer
* AZ - Availability zone

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
* 

#### Demo
* 2x EC2 & one DNS

[<img src="https://i.imgur.com/HZOEJ7E.png">](https://i.imgur.com/HZOEJ7E.png)

### ALB
* Default: 
