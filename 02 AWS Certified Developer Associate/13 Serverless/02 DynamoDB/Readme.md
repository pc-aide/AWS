# DynamodDB

## Acronym
* RDBMS - Relational database management system
* AZ - Availability Zone

## Terminology
* item = row

## Doc

## Intro
* NoSQL Serverless Database

---

## Traditional Architecture
* Traditional application leverage RDBMS databases
* These DBs have the SQL query language
* Strong requirements about how the data should be modeled
* Ability to do join, aggregations, computations
* Vertical scaling (means usually getting a more powerfull CPU/RAM/IO)

### Diagram
[<img src="https://i.imgur.com/yM5qLCE.png">](https://i.imgur.com/yM5qLCE.png)

---

## NoSQL databases
* NoSQL DBs are non-relational databases & are **distributed**
* NoSQL DBs include MongoDB, DynamoDB, etc 
* NoSQL DBs don't support **join**
* All the data is needed for a query is present in one row
* NoSQL DBs don't perform aggregaions such as "SUM"
* **NoSQL DBs scale horizontally**
* There's no "righ or wrong" for NoSQL vs SQL, they just require to model the data differently & think about use queies
  differently
  
---

## DynamoDB
* Fully Managed, Highly avaiable with replication across 3 AZs
* NoSQL db - not a relational db
* Scales to massive workloads, distributed db
* Millions of requests per seconds, trillions of row, 100s of TB of storage
* Fast & consistent in performance (low latency on tretrieval)
* Integrated with IAM for security, authorization & administration
* Enables event driven programming with DynamoDB Streams
* low cost & auto scaling capabilities

---

## DynamoDB - Basic
* DynamoDB is made of **tables**
* Each table has a **primary key** (must be decided at creation time)
* Each table can have an infinite number of items (=rows) 
* Each item has **attributes** (can be added over time - can be null)
* Maximum size of a item is 400 KB
* Data types supported are:
    * Scalar Types:
        * String
        * Number
        * Binary
        * Boolean
        * Null
    * Document type: 
        * List
        * Map
    * Set Types: 
        * String Set
        * Number Set
        * Binary Set

---

## Dynamo - Primary Keys
* **Option 1: Partition key only (HASH)**
* Partition key must be unique for each item
* Partition key must be "diverse" so that the data is distributed
* <ins>Example:</ins> user_id for a users table

* **Option: 2: Partiton key + Sort key**
* The combination must be unique 
* Data is grouped by partition key
* Sort key == range key
* <ins>Example:</ins> users-games table
    * user_id for the partion key
    * game_id for the sort key

### Diagram
[<img src="https://i.imgur.com/nfPG3vk.png">](https://i.imgur.com/nfPG3vk.png)
[<img src="https://i.imgur.com/kJRQ7ER.png">](https://i.imgur.com/kJRQ7ER.png)

---

## Partition Keys exercise
* We're building a movie db
* What is the best partition key to mazimize data distribution?
    * movie_id
    * producer_name
    * leader_actor_name
    * movie_language
* movie_id has the highest cardinality so it's a good candidate
* moving_lauge donesn't take may values & may be skewed towards English so it's not a great partition key
