# Kinesis Data Analytics

## Acronym
* ETL - Extrac, Transform, Load

## Intro
* Real-time processing & analysis of streams using SQL
* Time-series analytics, real-time dashboard, & real-time metrics
* Outputs to data Firehose, Lambda, & Data Streams

---

## Conceptually...
[<img src="https://i.imgur.com/wSpRhqq.png">](https://i.imgur.com/wSpRhqq.png)

---

## In more depth (zoom in)...
[<img src="https://i.imgur.com/sIF4fCM.png">](https://i.imgur.com/sIF4fCM.png)

---

## Kinesis Data Analytics
* Use cases
  * <ins>Streaming ETL</in>**select columns**, make simple transformations, on streaming data
  * <ins>Continuous metric generation</ins>: live leaderboard for a mobile game
  * <ins>Responsive analytics</ins>: look for certain criteria & build alerting (filtering)
* features
  * Pay only for resources consumed (but it's not cheap)
  * Serverless, scales automatically
  * Use IAM permissions to acccess streaming source & destination(s)
  * SQL or **Apache Flink** to write the computation
  * Schema discovery
  * Lambda can be used for pre-processing
