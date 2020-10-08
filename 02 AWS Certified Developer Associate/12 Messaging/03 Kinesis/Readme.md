# Kinesis

## Acronym
* IoT - Internet of Things
* AZ - Availability Zone
* SDK - Software Development Kit

## Doc

## Intro
* **Kinesis** is a managed alternative to Apache Kafka
* Great for application logs, metrics, IoT, clikcstreams
* Great for "**real-time**" big data
* Great for streaming processing frameworks (Spark, NiFi, etc...)
* Data is automatically replicated to 3 AZ

1) **Kinesis Streams:** low latency streaming ingest at scale
2) **Kinesis Analytics:** perform real-time analytics on streams using SQL
3) **Kinesis Firehose:** load streams into S3, Redshift, ElasticSearch...

---

## Topology
[<img src="https://i.imgur.com/G3kojyP.png">](https://i.imgur.com/G3kojyP.png)

---

## Kinesis Streams Intro
* Streams are divided in ordered Shards/Partitions
* Data retention is 1 day by default, can go up to 7 days
* Ability to reprocess/replay data
* Multiple applications can consume the same stream
* Real-time processing with scale of throughput
* Once data is inserted in Kinesis, it can't be deleted (immutability)

### Diagram
[<img src="https://i.imgur.com/PGs4aCl.png">](https://i.imgur.com/PGs4aCl.png)

---

## Kinesis Streams Shards
* One steam is made of many different shards
* 1 MB/s or 1k messages/s at write PER SHARD
* 2 MB/s at read PER SHARD
* Billing is per shard provisioned, can have as many shards as you want
* Batching available or per message calls
* The number of shards can evolve over time (reshard/merge)
* **Records are ordered per shard**

### Diagram
[<img src="https://i.imgur.com/KAAir2R.png">](https://i.imgur.com/KAAir2R.png)

---

## Kinesis API - Put records
* PutRecord API + Partition key that gets hashed
* The same key goes to the same partition (helps with ordering for a specific key)
* Messages sent get a "sequence number"
* Choose a partition key that is highly distributed (helps prevent "hot partition")
    * user_id if many users
    * **Not** country_id if 90% of the users are in one country
* Use Batching with PutRecords to reduce costs & increase throughput
* **ProvisionedThroughputExceeded** if we go over the limits
* Can use CLI, AWS SDK, or producer libraries from various frameworks

### Diagram
[<img src="https://i.imgur.com/spTcN7v.png">](https://i.imgur.com/spTcN7v.png)

---

## Kinesis API - Exceptions
* ProvisionedThroughputExceeded Exceptions
    * Happens when sending more data (exceeding MB/s or TPS for any shard)
    * Make sure you don't have a hot shard (such as your partition key is bad & too much data goes to that partition)
* Solution:
    * Retries with backoff
    * Increase shards (scaling)
    * Ensure your partition key is a good one
    
---

## Kinesis API - Consumers
* Can use a normal consumer (CLI, SDK, etc...)
* Can use Kinesis Client Library (in Java, Node, Python, Ruby, .NET)
    * KCL uses DynamoDB to checkpoint offsets
    * KCL uses DynamoDB to track other workers & share the work amongst shards
    
### Diagram
[<img src="https://i.imgur.com/r6UKzbv.png">](https://i.imgur.com/r6UKzbv.png)
