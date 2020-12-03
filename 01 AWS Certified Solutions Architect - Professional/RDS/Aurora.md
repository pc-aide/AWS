# Aurora

## Acronym
* RR - Read Replicas
* HA - High Availability
* RTO - Recovery Time Object
* M - Master
* HA - High Availability
* RDS - Relational Database Service
* AZ - Availability zone

## Intro
* **DB Engines**: PostgreSQL-compatible & MySQL-compatible
* **Storage**: automaticcaly grows up to 64TB, 6 copies of data, multi-AZ
* **Read Replicas**: up to 15 RR, reader endpoint to access them all
* **Cross Region RRR**: entire database is copied (not select tables)
* **Load/Offload data directly from/to S3**: efficient use of resources
* **BAckup, Snapshots & Restore**: same as RDS

---

## HA & Read Scaling
* 6 copies of your data across 3 AZ:
  * 4 copies out of 6 needed for writes
  * 3 copies out of  need for reads
  * Self healing with peer-to-peer replication
  * Storage is striped across 100s of volumes
* Automated failover for master in less than 30 seconds
* Master + up to 15 Aurora Read Replicas serve reads
* Support for Cross Region Replication
  
### Diagram
[<img src="https://i.imgur.com/11wJPFZ.png">](https://i.imgur.com/11wJPFZ.png)

---

## DB Cluster
[<img src="https://i.imgur.com/5opZBTd.png">](https://i.imgur.com/5opZBTd.png)

---

## Serverless
* Automated database instantiation & auto-scaling based on actual usage
* Good for infrequent, intermittent or unpredictable workloads
* No capacity planning needed
* Pay per second, can be more cost-effective

### Diagram
[<img src="https://i.imgur.com/jvFEcTS.png">](https://i.imgur.com/jvFEcTS.png)

---

## Global Aurora
* Aurora Cross Region Read Replicas:
  * Usefull for disaster recovery
  * Simple to put in place
* Aurora Global Database (recommended):
  * 1 Primary Region (read/write)
  * Up to 5 secondary (read-only) regions, replication lag is less than 1 second
  * Up to 16 Read Replicas per secondary region
  * Helps for decreasing latency
  * Promoting another region (fro disaster recovery) has an RTO of < 1 minute
  
### Diagram
[<img src="https://i.imgur.com/8BzKs37.png">](https://i.imgur.com/8BzKs37.png)

---

## Aurora Multi-Master
* In case you want immediate failover for write node (HA) - 
* Every node does R/W - vs promoting a RR as the new master

### Diagram
[<img src="https://i.imgur.com/AfI3szd.png">](https://i.imgur.com/AfI3szd.png)
