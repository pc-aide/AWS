# Demo Kinesis

## Acronym

## Doc
* [Resharding a Stream](https://docs.aws.amazon.com/streams/latest/dev/kinesis-using-sdk-java-resharding.html?icmpid=docs_console_unmapped)
* [UpdateShardCount](https://docs.aws.amazon.com/kinesis/latest/APIReference/API_UpdateShardCount.html?icmpid=docs_console_unmapped)

## Intro
* Note Kinesis $$$
* Kinesis\Get started\**Kinesis Data Streams**
    * Data stream name: Demo-Kinesis
    * Number of shards: 1
* Create Kinesis stream
    
    
[<img src="https://i.imgur.com/MwgzUFb.png">](https://i.imgur.com/MwgzUFb.png)
[<img src="https://i.imgur.com/ZXUfOX3.png">](https://i.imgur.com/ZXUfOX3.png)
[<img src="https://i.imgur.com/uy0VwEK.png">](https://i.imgur.com/uy0VwEK.png)
[<img src="https://i.imgur.com/MxO0sCp.png">](https://i.imgur.com/MxO0sCp.png)

* Demo-Kinesis:

[<img src="https://i.imgur.com/fJRrKFI.png">](https://i.imgur.com/fJRrKFI.png)

* Monitoring:

[<img src="https://i.imgur.com/YRN4LAm.png">](https://i.imgur.com/YRN4LAm.png)

* AWS CLI
````bash
aws kinesis help
````
[<img src="https://i.imgur.com/6Qnky7K.png">](https://i.imgur.com/6Qnky7K.png)

* list streams:
````bash
aws kinesis list-streams help
aws kenesis list-streams
````
[<img src="https://i.imgur.com/XIanTcm.png">](https://i.imgur.com/XIanTcm.png)
[<img src="https://i.imgur.com/2gEB1GK.png">](https://i.imgur.com/2gEB1GK.png)

* describe-streams
````bash
aws kinesis describe-stream help
````
[<img src="https://i.imgur.com/yhz1dSr.png">](https://i.imgur.com/yhz1dSr.png)

* stream-name
````bash
aws describe-stream --stream-name Demo-Kinesis
````
[<img src="https://i.imgur.com/D64buif.png">](https://i.imgur.com/D64buif.png)

* put-record
````bash
aws kinesis put-record help
````
[<img src="https://i.imgur.com/bkwu3Lj.png">](https://i.imgur.com/bkwu3Lj.png)
[<img src="https://i.imgur.com/3H9UNHe.png">](https://i.imgur.com/3H9UNHe.png)
[<img src="https://i.imgur.com/TLIIr2f.png">](https://i.imgur.com/TLIIr2f.png)

* sample put-record
````bash
aws kinesis put-record \
--stream-name Demo-Kinesis \
--data "user test" \
--partition-key user_123
````
[<img src="https://i.imgur.com/ZOr96GA.png">](https://i.imgur.com/ZOr96GA.png)

* Another message for example
````bash
aws kinesis put-record \
--stream-name Demo-Kinesis \
--data "user paul" \
--partition-key user_123
````

[<img src="https://i.imgur.com/sGtCk9B.png">](https://i.imgur.com/sGtCk9B.png)

* Note: Invalid based64: "user Login":
    * idem with user space: login, singup, sam, etc

[<img src="https://i.imgur.com/vB0EyX8.png">](https://i.imgur.com/vB0EyX8.png)

* Another message again:
````bash
aws kinesis put-record \
--stream-name Demo-Kinesis \
--data "home" \
--partition-key user_123
````
[<img src="https://i.imgur.com/OS6cHAS.png">](https://i.imgur.com/OS6cHAS.png)

* now we want to retrieve these messages
````bash
aws kinesis help
````
[<img src="https://i.imgur.com/bZ817Rs.png">](https://i.imgur.com/bZ817Rs.png)

* get-shard-iterator
````bash
aws kinesis get-shard-iterator help
````
[<img src="https://i.imgur.com/vlwfXnz.png">](https://i.imgur.com/vlwfXnz.png)
[<img src="https://i.imgur.com/ej6mbYu.png">](https://i.imgur.com/ej6mbYu.png)

* get-hsard-iterator-type:
````bash
aws kinesis get-shard-iterator \
--stream-name Demo-Kinesis \
--shard-id shardId-000000000000 \
--shard-iterator-type TRIM_HORIZON
````
[<img src="https://i.imgur.com/aqKPBQe.png">](https://i.imgur.com/aqKPBQe.png)

* shard-iterator <value>
````bash
aws kinesis get-records \
--shard-iterator <value>
````
[<img src="https://i.imgur.com/GNXrKT0.png">](https://i.imgur.com/GNXrKT0.png)
[<img src="https://i.imgur.com/QJ87V4b.png">](https://i.imgur.com/QJ87V4b.png)

* base 64 decode online
    * https://www.base64decode.org/
* i don't have blog text?!

[<img src="https://i.imgur.com/ftGZIZJ.png">](https://i.imgur.com/ftGZIZJ.png)
