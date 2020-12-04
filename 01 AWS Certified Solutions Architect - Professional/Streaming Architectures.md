# Streaming Architectures

## Acronym
* KDF - Kinesis Data Firehose
* KDS - Kinesis Data Streams
* KCL - Kinesis Client Library
* WCU - Write Capacity Unit
* SNS - Simple Notification Service
* FIFO - First In, Firt Out
* SQS - Simple Queue Service

## Full Data Engineering Pipeline Real-Time Layer
[<img src="https://i.imgur.com/pxqwkhj.png">](https://i.imgur.com/pxqwkhj.png)

---

## Streaming Architectures | 3k messages of 1KB per second
* Kinesis
  * 3 shards: 3MB/s in
  * 3* $0.015/hr = **$32.4/mth**
  * Must use KDF for output to S3
* DynamoDB + Streams
  * 3k WCU = 3MB/s
  * = **$1 450.9.0/month**
  * Storage in DynamoDB
  
### Diagram
[<img src="https://i.imgur.com/ipxBjwr.png">](https://i.imgur.com/ipxBjwr.png)

---

## Comparison Charts
|             | Kinesis Data<br>Streams                      | SQS                | SQS FIFO                    | SNS                               | DynamoDB                            | S3                                            |
| ----------- | -------------------------------------------- | ------------------ | --------------------------- | --------------------------------- | ----------------------------------- | --------------------------------------------- |
| Data        | Immutable                                    | Immutable          | Immutable                   | Immutable                         | Mutable                             | Mutable                                       |
| Retention   | 1-7 days,<br>export to S3<br>using KDF       | 1-14 days          | 1-14 days                   | No retention                      | Infinite or can<br>implement<br>TTL | Infinite, can<br>setup life cycle<br>policies |
| Ordering    | Per shard                                    | No ordering        | Per group-id                | No ordering                       | No ordering                         | No ordering                                   |
| Scalability | Provision<br>shards                          | Soft limit         | 300 msg/s<br>Or 3k if batch | Soft limit                        | WCU & RCU<br>On-demand              | Infinite<br>3.5k PUT 5.5k<br>GET / prefix     |
| Readers     | EC2, Lambda<br>KDF, KDA, KCL<br>(checkpoint) | EC, Lambda         | EC, Lambda                  | HTTP,<br>Lambda,<br>Email, SQS... | DynamoDB<br>Streams                 | SDK, S3<br>Events                             |
| Latency     | KDS (200 ms)<br>KDF (1 min)                  | Low (10-<br>100ms) | Low (10-<br>100ms)          | Low (10-<br>100ms)                | Low (10-<br>100ms)                  | Low (10-<br>100ms)                            |

