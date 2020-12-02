# DynamoDB

## Acronym
* RPS - Requests Per Second
* IAM - Identity & Access Management
* ACID - Atomic, Consistency, Integration, & Durability
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
* Object = <ins>
