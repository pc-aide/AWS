# ElastiCache

## Acronym
* RDS - Relational database service
* AZ - Availability Zone
* HA - High Availability
* AOF - Append Only Files

## Doc
* [Append Only Files (AOF) in ElastiCache for Redis](https://docs.aws.amazon.com/AmazonElastiCache/latest/red-ug/RedisAOF.html)

## Introduction
* The same way RDS is to get managed Relational DBs...
* ElastiCahce is to get managed Redis or Memcached
* Aches are in-memory DBs with really high performance, low latency
* Helps reduce load off of DBs for read intensive workloads
* Helps make your application stateless
* Write Scaling using sharding
* Multi AZ with Failover Capability
* AWS takes care of OS maintenance / pathcing, optimizations, etup, configuration, monitoring, failure recovery & backups

---

## Solution Architecture
### DB Cache
* Appliactions queries ElastiCache, if not available, get from RDS & store in ElastiCache
* Helps relieve load in RDS
* Cache must have an invalidation strategy to make sure only the most current data is used in there

#### Topology
[<img src="https://i.imgur.com/BBelyAe.png">](https://i.imgur.com/BBelyAe.png)


### User Session Store
* User logs into any of the application
* The application writes the session data into ElastiCache
* The user hits another instance of our application
* The instance retrieves the data & the user is already logged in

#### Topology
[<img src="https://i.imgur.com/317eQ28.png">](https://i.imgur.com/317eQ28.png)

---

## Redis vs Memcached
* REDIS
    * Multi AZ with Auto-Failover
    * Read Replicas to scale reads & have HA
    * Data Durability using AOF persistence
    * Backup & restore features
    
* MEMCACHED
    * Multi-node for partitioning of data (sharding)
    * **Non persistent**
    * No backup & resotre 
    * Multi-threaded architecture

### Topology
[<img src="https://i.imgur.com/JTCJ6PZ.png">](https://i.imgur.com/JTCJ6PZ.png)
