# Kinesis Data Firehose

## Acronym
* ES - ElasticSearch

## Intro
* Fully Managed Service, no administration, automatic scaling, serverless
* **Near Real Time** (60 seconds latency minimum for non full batches)
* Load data into Redshift/S3/ES/Splunk
* the goal is:
  * to ingest data at scale in..
* Pay for the amount of data going through Firehose
* Outputs to data services like S3, Amazon Redshift, ElasticSearch, & Splunk
* Can output raw data or transform data before delivery
* Stores data up to 24 hours in case of delivery failures

### Diagram
[<img src="https://i.imgur.com/8YMPxXn.png">](https://i.imgur.com/8YMPxXn.png)
[<img src="https://i.imgur.com/uIZs1Dq.png">](https://i.imgur.com/uIZs1Dq.png)

---

## Delivery Diagram
[<img src="https://i.imgur.com/s2cVQjA.png">](https://i.imgur.com/s2cVQjA.png)

---

## Firehose Buffer Sizing
* Firehose accumulates records in a buffer
* The buffer is flushed based on time & size rules
* **Buffer Size (ex:32MB**): if that buffer size is reached, it's flushed
* **Buffer Time (ex:1 min**): if that time is reached, it's flushed
* Firehose can automatically increase the buffer size to increase throughput
* High throughput => Buffer Size will be hit
* Low throughput => Buffer Time will be hit
* If real-time flush from Kinesis Data Streams to S3 is needed, use Lambda 

---

## Kinesis Data Streams vs Firehose
* Streams
  * Going to write custom code (producer/consumer)
  * Real time (~200ms latency for classic, ~70ms latency for enchanced fan-out)
  * Must manage scaling (shard splitting/merging)
  * Data Storage for 1 to 7 days, replay capability, multi consumers
  * Use with Lambda to insert data in real-time to ES (for example)
* Firehose
  * Fully managed, send to S3, Splunk, Redshift, ES
  * Serverless data transformations with Lambda
  * **Near** real time (lowest buffer time is 1 min)
  * Automated Scaling
  * No data storage
