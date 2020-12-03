# RDS

## Acronym
* RDS - Relational Database Service
* IAM - Identity & Access Management
* SSL - Secure Sockets Layer
* TDE - Transparent Data Encryption
* KMS - Key Management Service
* AZ - Availability Zone
* SG - Security Group
* SNS - Simple Notification Service

## Intro
* Engines:
  1) MySQL
  2) PostgreSQL
  3) Microsoft SQL
  4) Oracle
  5) MariaDB
  6) Aurora
* Managed DB
  * provisioning, backups, patching, monitoring
* **Launched within a VPC**, usually in **private subnet**, control network access using SGs (important when using Lambda)
* **Storage by EBS** (gp2 or io1), can increase volume size with auto-scaling
* **Backups**: automated with point-in-time recovery. Backups expire
* **Snapsots**: manual, can make copies of snapshots cross region
* **RDS Events**: get notified vis SNS for events (operations, outages...)

---

## Mutli AZ & Read Replicas
* **Multi-AZ**: Standby instance for failover in case of outage
* **Read Replicas**: Increase read throughput. Eventual consistency. Can be <ins>cross-region</ins>

### Diagram
[<img src="https://i.imgur.com/yO0SOdS.png">](https://i.imgur.com/yO0SOdS.png)

---

## Security (reminder)
* KMS encryption at rest for underlying EBS volumes/snapshots
* TDE for Oracle & SQL Server
* SSL encryption to RDS is possible for all DB (**in-flight**)
* IAM authentication for MysQL & PostgreSQL
* Authorization still happens within RDS (not in IAM)
* Can copy an un-encrypted RDS snapshot into an encrypted one
* CloudTrail can't be used to track queries made within RDS

---

## Cross Region Failover
[<img src="https://i.imgur.com/Pp0NnZK.png">](https://i.imgur.com/Pp0NnZK.png)
