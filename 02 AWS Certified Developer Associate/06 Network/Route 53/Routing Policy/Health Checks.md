# Health Checks

## Acronym
* ALB - Application Load Balancing
* SG - Security Group

## Doc
* [Monitoring health check status and getting notifications](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/health-checks-monitor-view-status.html#monitoring-health-checks)
* [Configuring DNS failover](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/dns-failover-configuring.html)

## Introduction
* Have X health checks failed => unhealthy (default 3)
* After X health checks passed => health (default 3)
* Default health check interval: 30s (can set to 10s - higher cost)
* **About 15 health checkers will check the endpoint health**
* => one request every 2s on average
* Can have HTTP, TCP & HTTPS health checks (no SSL verification)
* Possibility of integrating the health check wih CloudWatch
* Health chekcs can be linked to Route 53 DNS queries!

---

## Demo
* Route 53\Health chekcs\Create helth check:

[<img src"https://i.imgur.com/gWtcoEV.png">](https://i.imgur.com/gWtcoEV.png)

* Name: Ca-Central-Health-Check
* What to monitor: Endpoint
* Protocol: HTTP
* Specify endpoint by: IP
* IP address: \<YourIP\>
* Other values: default

[<img src="https://i.imgur.com/mFOVN7d.png">](https://i.imgur.com/mFOVN7d.png)
[<img src="https://i.imgur.com/39fZJ0A.png">](https://i.imgur.com/39fZJ0A.png)

* Idem for another region:

[<img src="https://i.imgur.com/pqIFGz7.png">](https://i.imgur.com/pqIFGz7.png)
[<img src="https://i.imgur.com/DQiafiO.png">](https://i.imgur.com/DQiafiO.png)
[<img src="https://i.imgur.com/rm41fNS.png">](https://i.imgur.com/rm41fNS.png)


* Your Browser:

[<img src="https://i.imgur.com/OOGL67w.png">](https://i.imgur.com/OOGL67w.png)
[<img src="https://i.imgur.com/vgZd9vn.png">](https://i.imgur.com/vgZd9vn.png)
