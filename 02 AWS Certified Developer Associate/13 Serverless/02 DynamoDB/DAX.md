# DAX

## Acronym
* DAX - DynamoDB Accelerator
* AZ - Availability Zone
* KMS - Key Management Service
* VPC - Virtual Private Cloud
* IAM - Identity & Access Management

## Doc

## Intro
* DAX
* Seamless cache for DynamoDB, no application re-write
* Writes go through DAX to DynamoDB
* Micro second latency for cached reads & queries
* Solves the Hot Key problem (too many reads)
* 5 minutes TTL for cache by default
* Up to 10 nodes in the cluster
* Multi AZ (3 nodes minimum recommended for production)
* Secure (Encrypton at rest with KMS, VPC, IAM, cloudTrail...)

### Diagram
[<img src="https://i.imgur.com/2j0wdCA.png">](https://i.imgur.com/2j0wdCA.png)

---

## DAX vs ElastiCache
[<img src="https://i.imgur.com/061c1Pa.png">](https://i.imgur.com/061c1Pa.png)

---

## Demo
* DynamoDB\DAX
    * Dashboard

[<img src="https://i.imgur.com/nWOtfVd.png">](https://i.imgur.com/nWOtfVd.png)

* create cluster (just overview - nothing to do)

[<img src="https://i.imgur.com/WBA5xL3.png">](https://i.imgur.com/WBA5xL3.png)
