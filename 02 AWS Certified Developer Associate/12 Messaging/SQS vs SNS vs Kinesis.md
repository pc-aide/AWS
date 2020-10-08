# SQS vs SNS vs Kinesis

## Acronym
* SQS - Simple Queue Service
* SNS - Simple Notification Service
* FIFO - First In First Out
* Pub/Sub - Publish Subscribe
* ETL - Extrac, Transform, Load

## Doc

## Diagram
1) SQS
    * Consumer "pull data"
    * Data is deleted after being consumed
    * Can have as many workers (consumers) as we want
    * No need to provision throughput
    * No ordering guarantee (except FIFO queues)
    * Individual message delay capability
2) SNS
    * Push data to many subscribers
    * Up to 10 Millions subscribers
    * Data is not persisted (lost if not delivered)
    * Pub/Sub
    * Up to 100k topics
    * No need to provision throughput
    * Integrates with SQS for fan-out architecture pattern
3) Kinesis
    * Consumers "pull data"
    * As many consumers as we want
    * Possibility to replay data
    * Meant for real-time big data, analytics & ETL
    * Ordering at the shard level
    * Data expires after X days
    * Must provision throughput
