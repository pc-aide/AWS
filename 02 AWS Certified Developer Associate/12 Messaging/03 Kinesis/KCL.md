# KCL

## Acronym
* KCL - Kenesis Client Library
* IAM - Identity & Access Management
* EB - Elastic Beanstalk

## Doc

## Kinesis KCL in Depth
* KCL is Java library that helps read record from a Kinesis Streams with distributed applications sharing the read workload
* <ins>Rule: each shard is be read by only one KCL instance</ins>
* Means 4 shards = max 4 KCL instances
* Means 6 shards = max 6 KCL instances
* Progress is checkpointed into DynamoDB (need IAM access)
* KCL can run on EC2, EB, on Premise Application
* <ins>**Records are read in order at the shard level**</ins>

---

## KCL Example: 4 shards
[<img src="https://i.imgur.com/0wlxCvC.png">](https://i.imgur.com/0wlxCvC.png)

---

## KCL Example: 4 shards, scaling KCL app
[<img src="https://i.imgur.com/lUzHamO.png">](https://i.imgur.com/lUzHamO.png)

---

## KCL Example: 6 shards, scaling Kinesis
[<img src="https://i.imgur.com/IZtPpPS.png">](https://i.imgur.com/IZtPpPS.png)

---

## KCL Example: 6 shards, scaling KCL
[<img src="https://i.imgur.com/AejtPT1.png">](https://i.imgur.com/AejtPT1.png)
