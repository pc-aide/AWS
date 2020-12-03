# Kinesis Data Streams

## Acronym
* IoT - Internet of Things
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

## 
