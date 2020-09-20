# Aurora

## Acronym
* DB - database
* HA - High Availability
* KMS - Key Management Service
* SG - Security Group
* DR - Disaster Recovery
* RTO - Recovery Time Objective

## Doc

## Introduction
* Aurora is a proprietary technology from AWS (not open sourced)
* Postgres & MysQL are both supported as Aurora DB (that means your drivers will work as if Aurora
  was a Postgres or MysQL db)
* Aurora is "AWS cloud optimized" & claims 5x performance improvement over MysQL on RDS, over 3x ther performance of Postgres on RDS
* Aurora storage automatically gorws in increments of 10 GB, up to 64 TB
* Aurora can have 15 replicas while MySQL has 5, & the replication process is faster (sub 10ms replica lag)
* Failover in Aurora is instantaneous. It's HA native
* Aurora costs more than RDS (20% more) - but is more efficient

---

## Aurora HA & Read Scaling
* 6 copies of your data across 3 AZ:
    * 4 copies out of 6 needed for writes
    * 3 copies out of 6 need for reads
    * Self healing with peer-to-peer replication
    * Storage is striped across 100s of volumes
* One Aurora Instance takes writes (master)
* Automated failover for master in less than 30 seconds
* Master + up to 15 Aurora Read Replicas serve reads
* Support for Cross Region Replication
    
### Topology 
[<img src="https://i.imgur.com/XoHRCGM.png">](https://i.imgur.com/XoHRCGM.png)

---

## Aurora DB Cluster
* Writer Endpoint
    * Pointing to the master
* Reader Endpoint
    * Connection Load Balancing

### Topology
[<img src="https://i.imgur.com/2WJBKwM.png">](https://i.imgur.com/2WJBKwM.png)

--- 

## Features of Aurora
* Automatic fail-over
* Backup & Recovery
* Isolation & security
* Industry compliance
* Push-button scaling
* Automated Patching with Zero Downtime
* Advanced Monitoring
* Routine Maintenance
* Backtrack: restore data at any point of time without using backups
    * e.g Restore yesterdays 5 PM
    
--- 

## Aurora Security
* Similar to RDS because uses the same engines
* Encryption at rest using KMS
* Automated backups, snapshots & replicas are also encrypted
* Encryption in fligh using SSL (same process as MySQL or Postgres)
* **Possibility to authenticate using IAM toke (same method as RDS)**
* You are responsible for protecting the instance with SGs
* You can't SSH

---

## Aurora Serverless
* Automated db instantiation & auto-scaling based on actual usage
* Good for infrequent, intermittent or unpredictable workloads
* No capacity planning needed
* Pay per second, can be more cost-effective

### Topology
[<img src="https://i.imgur.com/eSM1qJi.png">](https://i.imgur.com/eSM1qJi.png)
[<img src="https://i.imgur.com/y19J1yz.png">](https://i.imgur.com/y19J1yz.png)
[<img src="https://i.imgur.com/1eYJj4q.png">](https://i.imgur.com/1eYJj4q.png)
[<img src="https://i.imgur.com/H6hRBhk.png">](https://i.imgur.com/H6hRBhk.png)

---

## Global Aurora
* Aurora Cross Region Read Replicas
    * Useful for DR
    * Simple to put in place
* Aurora Global DB (recommended):
    * 1x Primary Region (read / write)
    * Up to 5 secondary (read-only) regions, replication lag is less than 1 second
    * Up to 16 Read Replicas per secondary region
    * Helps for decreasing latency
    * Promiting another region (for DR) has an RTO of < 1 minute
    
### Topology
[<img src="https://i.imgur.com/vKzDwqJ.png">](https://i.imgur.com/vKzDwqJ.png)
