# Disaster Recovery

## Acronym
* AZ - Availability Zone
* CRR - Cross Region Replication
* DR - Disaster Recovery
* EBS - Elastic Block Store
* EFS - Elastic File System
* ELB - Elastic Load Balancer
* HA - High Availability
* IA - Infrequently Access
* RDS - Relational Database Service
* RPO - Recovery Point Objective
* RTO - Recovery Time Objective

## Intro
* Any event that has a negative impact on a company's business continuity or finances is a disaster
* DR is about preparing for & recovering from a disaster
* What kind of DR?
  * On-premise => On-premise: traditional DR, & very expensive
  * On-premise = > AWS Cloud: hybrid recovery
  * AWS Cloud Region A => AWS Cloud Region B
* Need to define two terms:
  * RPO: Recovery Point Objective
  * RTO: Recovery Time Objective
  
---

## RPO & RTO
[<img src="https://i.imgur.com/LBoWai6.png">](https://i.imgur.com/LBoWai6.png)

---

## DR Strategies
* Backup & Restore
* Pilot Light
* Warm Standby
* Hot Site/Multi Site Approach

### Diagram
[<img src="https://i.imgur.com/HFWbhJk.png">](https://i.imgur.com/HFWbhJk.png)

---

## Backup & Restore (High RPO)
[<img src="https://i.imgur.com/P6isKon.png">](https://i.imgur.com/P6isKon.png)

---

## DR - Pilot Light
* A small version of the app is always running in the cloud
* Useful for the critical core (pilot light)
* Very similar to Backup & Restore
* Faster than Backup & Restore as critical systems are already up

### Diagram
[<img src="https://i.imgur.com/JDAg1AL.png">](https://i.imgur.com/JDAg1AL.png)

---

## Warm Standby
* Full system is up & running, but at minimum size
* Up disaster, we can scale to production load
* Expensive:
  * EC2 Auto Scaling
  * RDS Slave
  * ELB
* we increase your RPO, & RTO

### Diagram
[<img src="https://i.imgur.com/qFA1L9U.png">](https://i.imgur.com/qFA1L9U.png)

---

## Multi Site / Hot Site Approach
* Very low RTO (minutes or seconds) - very expensive
* Full Production Scale is running AWS & On Premise

### Diagram
[<img src="https://i.imgur.com/3b7Q12N.png">](https://i.imgur.com/3b7Q12N.png)

---

## All AWS Multi Region
[<img src="https://i.imgur.com/UScTSu8.png">](https://i.imgur.com/UScTSu8.png)

---

## DR Tips
* **Backup**
  * EBS Snapshots, RDS automated backups/Snapshots, etc...
  * Regular pushes to S3/S3 IA/Glacier,Lifecycle Policy, Cross Region Replication
  * From On-Premise: Snowball or Storage Gateway
* **HA**
  * Use Route 53 to migrate DNS over from Region to Region
  * RDS Multi-AZ, ElastiCache Multi-AZ, EFS, S3
  * Site to Site VPN as a recovery from Direct Connect
* **Replication**
  * RDS Replication (Cross Region), AWS Aurora + Global Databases
  * Database replication from on-premise to RDS
  * Storage Gateway
* **Automation**
  * CloudFormation/Elastic Beanstalk to re-create a whole new environment
  * Recover/Reboot EC2 instances with CloudWatch if alarms fail
  * AWS Lambda functions for customized automations
* **Chaos**
  * Netflix has a "simian-army" randomly terminating EC2
