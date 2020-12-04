# Kinesis Data Streams

## Acronym
* IoT - Internet of Things
* KCL - Kinesis Client Library
* KPL - Kinesis Producer Library
* AZ - Availability Zone

## Intro
* Kinesis is a managed "data **streaming**" service
* Great for application logs, metrics, IoT, clickstreams
* Great for "real-time" big data
* Great for streaming processing frameworks (Spark, NiFi, etc...)
* Data is automatically replicated synchronously to 3 AZ
1) **Kinesis Streams**: 
  * low latency streaming ingest at scale
2) **Kinesis Analytics**: 
  * perform real-time analytics on streams using SQL
3) **Kinesis Firehose**:
  * load streams into S3, Redshift, ElasticSearch & Splunk
  
---

## Arhitecture
[<img src="https://i.imgur.com/B4EQSFg.png">](https://i.imgur.com/B4EQSFg.png)

---

## Kinesis Streams Overview
* Streams are divided in ordered **Shards/Partition**
* Data retention is 24 hours by default, can go up to 7 days
* Ability to reprocess/replay data
* Multiple applications can consume the same stream
* Real-time processing with scale of throughput
* Once data is inserted in Kinesis, it can't be deleted (immutability)

### Diagram
[<img src="https://i.imgur.com/pdDb9Po.png">](https://i.imgur.com/pdDb9Po.png)

---

## Shards
* One stream is made of many different shards
* Billing is per shard provisioned, can have as many shards as you want
* Batching available or per message calls
* The number of shards can evolve over time (reshard/merge)
* **Records are ordered per shard**

### Diagram
[<img src="https://i.imgur.com/fiQhoPH.png">](https://i.imgur.com/fiQhoPH.png)

---

## Kinesis Producers & Consumers
* <ins>**KINESIS PRODUCERS**</ins>
  * AWS SDK: simple producer
  * **Kinesis Producer Library**: batch, compression, retries, c++, Java
* **Kinesis Agent**:
  * Monitor log files & sends them to Kinesis directly
  * can write to Kinesis Data Streams <ins>**AND**</ins> Kinesis Data Firehose
* <ins>**KINESIS COMSUMERS**</ins>
  * AWS SDK: simple consumer
  * Lambda: (through Event source mapping)
  * KCL: checkpoint, coordinated reads
  
### Diagram
[<img src="https://i.imgur.com/oYjL3i5.png">](https://i.imgur.com/oYjL3i5.png)

---

## Limits
* Producer:
  * 1MB/s or 1k messages/s at write PER SHARD
  * "ProvisionedThroughputException" otherwise
    * add shar for more throughput
* Consumer Classic:
  * 2MB/s at read PER SHARD across all consumers
  * 5 API calls per second PER SHARD across all consumers
* Consumer Enchanced Fan-Out:
  * 2MB/s at read PER SHARD, PER ENHANCED CONSUMER
  * No API calls needed (push model)
* Data Retention:
  * 24 hours data retention by default
  * Can be extentended to 7 days
