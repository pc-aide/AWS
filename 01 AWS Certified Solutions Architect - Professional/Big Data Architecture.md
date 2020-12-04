# Big Data Architecture

## Acronym
* EMR - Elastic MapReduce
* IoT - Internet of Things
* EBS - Elastic Block Store

## Full Data Engineering Pipeline Analytics layer
[<img src="https://i.imgur.com/dXSvYz8.png">](https://i.imgur.com/dXSvYz8.png)

---

## Big Data Ingestion Pipeline
[<img src="https://i.imgur.com/qlr057z.png">](https://i.imgur.com/qlr057z.png)

---

## Comparison of warehousing technologies
* EMR
  * Need to use Big Data tools such as Apache Hive, Spark
  * One long-running cluster, many jobs, with auto-scaling, or one cluster per job?
  * Purchasing options  
    * Spot
    * On-demand
    * Reserved instances
  * Can access data in DynamoDB & / or S3
  * Scratch data on EBS disks (HDFS) & long term storage in S3 (EMRFS)
* Athena
  * Simple queries & aggregations, data must live in S3
  * Serverless, simple SQL queries, out-fo-the-box queries for many services (cost & billing...)
  * Audit queries through CloudTrail
* Redshift
  * Advanced SQL queries, must provision servers
  * Can leverage Redshift Spectrum for serverless queries on S3
