# DynamoDB

## Acronym
* RPS - Requests Per Second
* AZ - Availability Zone
* KMS - Key Management Service
* DAX - DynamoDB Accelerator
* DR - Disaster Recovery
* GSI - Global Secondary Index
* TTL - Time To Live
* LSI - Local Seconday Index
* IAM - Identity & Access Management
* ACID - Atomic, Consistency, Integration, & Durability
* RDS - Relational Database Service
* WCU - Write Capacity Unit
* RCU - Read Capacity Unit
* CRUD - Create,Read,Update, & Delete

## In short
* NoSQL database, fully managed, massive scale (1M RPS)
* Similar to Apache Cassandra (can migrate to DynamoDB)
* No disk space to provision, max object size is 400 KB
* Capacity: provisioned (WCU, RCU, & Auto Scaling) or on-demand
* Supports CRUD operations
* Read: eventually or strong consistency
* Supports transactions across multiple tables (ACID support)
* Backups available, point in time recovery
* Integrated with IAM for security

---

## Basic
* DynamoDB is made of **tables**
* Each table has a **prmary key** (must be decided at creation time)
* Each table can have infinite number of items (=rows)
* Each item has **attributes** (can be added over time - can be null)
* Maximum size of a item is **400KB**
* Data types supported are:
  * Scalar Type: String, Number, Binary, Boolean, Null
  * Document Types: List, Map
  * Set Types: String Set, Number Set, Binary Set
  
---

## Primary Keys
### Option 01 - Partition key only (HASH)
* Partition key must be unique for each item
* Partition key must be "diverse" so that the data is distributed
* <ins>Example:</ins> user_id for a users table

#### Diagram
[<img src="https://i.imgur.com/1Rsp1Yu.png">](https://i.imgur.com/1Rsp1Yu.png)

---

### Option 02 - Sort key
* Partion key + Sort key
* The combination must be unique
* Data is grouped by partition key
* Sort key == range key
* <ins>Example:</ins> users-games table
  * user_id for the partition key
  * game_id for the sort key
* **Example good sort key: timestamp**

#### Diagram
[<img src="https://i.imgur.com/9GIva7s.png">](https://i.imgur.com/9GIva7s.png)

---

## Indexes
* Object = <ins>primary key + optional sort key</ins> + attributes
* LSI
  * Keep the same primary key
  * Select an alternative sort key
  * Must be defined at table creation time
* GSI
  * Change the primary key & optonal sort key
  * Can be defined after the table is created
* You can only quey by PK + sort key on the main table & indexes (≠ RDS)

---

## Important Features
* TTL: automatically expire row after a specified epoch data
* DynamoDB **Streams**:
  * react to changes to DynamoDB tables in real time
  * Can be read by Lambda, EC2...
  * 24 hours retention of data
* **Global Tables**: 
  * Cross region replication
    * Active Active Replication, many regions
    * Must enable DynamoDB Streams
    * Useful for low latency, DR purposes
  
### Diagram
[<img src="https://i.imgur.com/8gJeBH6.png">](https://i.imgur.com/8gJeBH6.png)

---

## Indexing objects in DynamoDB
[<img src="https://i.imgur.com/xJEArLf.png">](https://i.imgur.com/xJEArLf.png)

---

## DAX
* Seamless cache for DynamoDB, no application re-write
* Writes go through DAX to DynamoDB
* Micro second latency for cached reads & queries
* Solves the Hot Key problem (too many reads)
* 5 minutes TTL for cache by default
* Up to 10 nodes in the cluster
* Multi AZ (3 nodes minimum recommended for production)
* Secure (Encryption at rest with KMS, VPC, IAM, CloudTrail...)

### Diagram
[<img src="https://i.imgur.com/Rltd4cY.png">](https://i.imgur.com/Rltd4cY.png)

---

## DAX vs ElastiCache
[<img src="https://i.imgur.com/H5yUFUQ.png">](https://i.imgur.com/H5yUFUQ.png)
