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
      * for ALB & NLB
* Time to comple "in-flight requests" while the instance is de-registering or **unhealthy**
* Stops sending new requests to the instance which is de-registering
* Between 1 to 3600 seconds, default is 300 seconds
* Can be disabled (set value to 0)
* Set to a low value if your requests are short

### Topology
[<img src="https://i.imgur.com/BAKTb98.png">](https://i.imgur.com/BAKTb98.png)

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

* even if start again my http, my status still unhealthy

##### log (s3)
* new log each 5min or higher for the trigger

[<img src="https://i.imgur.com/9iUfCqg.png">](https://i.imgur.com/9iUfCqg.png)
* don't have IP private for EC2Ama-02 (because stop httpd):

[<img src="https://i.imgur.com/mXEkanj.png">](https://i.imgur.com/mXEkanj.png)

* now - after 5min for new one log, i have my 2x instances :
* the log like a little "/var/log/httpd/access_log"

[<img src="https://i.imgur.com/a75m35C.png">](https://i.imgur.com/a75m35C.png)
[<img src="https://i.imgur.com/V3oNnTr.png">](https://i.imgur.com/V3oNnTr.png)

#### ALB
* Default:

#### NLB
* Default:
