# ELB - Connection Draining

## Acronym
* ELB - Elastic Load Balancer
* CLB - Classic Load Balancer
* NLB - Network Load Balancer

## Doc
* [Configure connection draining for your CLB](https://docs.aws.amazon.com/elasticloadbalancing/latest/classic/config-conn-drain.html?icmpid=docs_elb_console)
* [Access logs for your CLB](https://docs.aws.amazon.com/elasticloadbalancing/latest/classic/access-log-collection.html?icmpid=docs_elb_console)

## Introduction
* Feature naming: 
    * CLB : Connection Draining
    * Target Group: Deregistration Delay
      * fro ALB & NLB
* Time to comple "in-flight requests" while the instance is de-registering or **unhealthy**
* Stops sending new requests to the instance which is de-registering

## Demo
* healthy for ALB:

[<img src="https://i.imgur.com/TO0DZis.png">](https://i.imgur.com/TO0DZis.png)

* unhealthy for NLB:

[<img src="https://i.imgur.com/eAFx8Fh.png">](https://i.imgur.com/eAFx8Fh.png)

### Connection Draining
#### CLB
* Default: Connection Draining:Enabled, 300 seconds

[<img src="https://i.imgur.com/wkwSWx5.png">](https://i.imgur.com/wkwSWx5.png)

* we stope our 2x EC2 (simulation about some isssue)

[<img src="https://i.imgur.com/BRoVLYg.png">](https://i.imgur.com/BRoVLYg.png)

* Wait after ~1min (connection draining):

[<img src="https://i.imgur.com/drzPLzp.png">](https://i.imgur.com/drzPLzp.png)

* or just one EC2 is down or issue with request client:

[<img src="https://i.imgur.com/bYJ7gse.png">](https://i.imgur.com/bYJ7gse.png)

* if we stop httpd on EC2Ama-02:

[<img src="https://i.imgur.com/4E4utbW.png">](https://i.imgur.com/4E4utbW.png)
[<img src="https://i.imgur.com/ILYuQn6.png">](https://i.imgur.com/ILYuQn6.png)

#### ALB
* Default:

#### NLB
* Default:
