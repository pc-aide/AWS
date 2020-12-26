# Network Performance

## Acronym
* AZ - Availability Zone
* EBS - Elastic Block Store
* HA - High Availability
* MTU - Maximum Transmission Unit

## Intro
* Based on instance size
  * 100Gbps is current maximum
* EBS-Optimized dedicated storage bandwidth
* Baseline & burstable (e.g. familly "t2" -> eg. -> t2.micro)
* Advanced Networking Features

---

## Advanced Networking Features
* Enhanced Networking
* Network MTU
* Placement Groups

---

## Placement Groups
1) Cluster
  * 1x blue -> single rack of servers within the data center inside AZ
    * if the rack fail, so all EC2 will fails too
2) Partition
  * 2x blues -> two racks of servers within the data center inside AZ
    * if one of two rack fail, one some EC2 will fail not all of them
3) Spread
  * garante separated rack for our EC2 instance for maximum HA

### Diagram
[<img src="https://i.imgur.com/895Npnt.png">](https://i.imgur.com/895Npnt.png)
