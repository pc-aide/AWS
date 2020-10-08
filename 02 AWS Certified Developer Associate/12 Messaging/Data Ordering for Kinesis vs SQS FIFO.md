# Data Ordering for Kinesis vs SQS FIFO

## Acronym
* SQS - Simple Queue Service
* FIFO - First In First Out
* STD - Standard

## Doc
* [Solving Complex Ordering Challenges with Amazon SQS FIFO Queues](https://aws.amazon.com/blogs/compute/solving-complex-ordering-challenges-with-amazon-sqs-fifo-queues/)

## Ordering data into Kinesis
* Imagine you have 100 trucks (truck_1, truck_2,...,truck_100) on the road sending their GPS positions regularly into AWS
* You want to consume the data in order for each truck, so that you can track their movement accurately
* How should you send that data into Kinesis?
* **Answer**: send using a "**Partition Key**" value of the "truck_id"
* The same key will always go to the same shard

### Diagram
[<img src="https://i.imgur.com/8k0QnDQ.png">](https://i.imgur.com/8k0QnDQ.png)

---

## Ordering data into SQS
* For SQS std, there is no ordering
* For SQS FIFO, if you don't use a Group ID, messages are consumed in the order they are sent, **with only one consumer**
* Example:

[<img src="https://i.imgur.com/NP9v1HU.png">](https://i.imgur.com/NP9v1HU.png)

* You want to scale the number of consumers, but you want messages to be "grouped" when they are related to each other
* Then you use a Group ID (similar to Partition Key in Kinesis)
* Example:

[<img src="https://i.imgur.com/WpGcoKS.png">](https://i.imgur.com/WpGcoKS.png)

---

## Kinesis vs SQS ordering
* Let's assume 100 trucks, 5 kinesis shards, 1 SQS FIFO
* <ins>Kinesis Data Streams:</ins>
    * On average you'll have 20 trucks per shard
    * Trucks will have their data ordered within each shard
    * The maximum amount of consumers in parallel we can have is 5
    * Can receive up to 5 MB/s of data
* <ins>SQS FIFO</ins>
    * You only have on SQS FIFO queue
    * You will have 100 Group ID
    * You can have up to 100 Consumers (due to the 100 Group ID)
    * You have up to 300 messages per second (or 3k if using batching)
