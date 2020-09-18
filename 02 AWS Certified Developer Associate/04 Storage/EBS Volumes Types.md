# EBS Volumes Types

----------------

## Doc
* [Instances built on the Nitro System](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/instance-types.html?icmpid=docs_ec2_console#ec2-nitro-instances)
* [Amazon EBS volume types](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ebs-volume-types.html?icmpid=docs_ec2_console)

----------------

## Acronym

----------------

## Volume Type

### GP2
* Recommended for most workloads
* System boot volumes
* Virtual desktops
* Low-latency interactive apps
* Development & test environments
* 1 GiB - 1t TiB
* Small gp2 volumes can burst IPS to 3000
* Max IOPS is 16 000
* 3 IOPS per GB, means at **5 334 GB** (16002 IOPS -> 16000 IOPS because it's the max) we are at the max IOPS
* Min: 1Gib & max 16 TB

#### IOPS
* minimum 100 / 3000
* so  ∀x, where x∈ℕ* still 100 (IOPS)
  * ex.: 1..33 -> IOPS -> 100 / 3000

[<img src="https://i.imgur.com/Amy17AR.png">](https://i.imgur.com/Amy17AR.png)

* after 33, so the formula it's y*3 to know our IOPS, with max 3000
* so the max it's for IOPS 1600 with 16 384 GiB (size)

[<img src="https://i.imgur.com/YP1AmOa.png">](https://i.imgur.com/YP1AmOa.png)

----------------

### IO1
* Critical business applications that require sustained IOPS performance, or more than 16 000 IOPS per volume (gp2 limit)
* Large database workloads, such as:
    * MongoDB, Cassandra, Microsoft SQL Server, MySQL, PostgreSQL, Oracle
* Min: 4 Gib & max 16 TiB
* IOPS is provisioned (PIOPS) - Min 100 - Max 64 000 (Nitro instances) else Max 32 000 (other instances)
* The maximum ratio of provisioned IOPS to requested volume size (in GiB) is 50:1

#### IOPS
* Size (GB)
    * Min 4  & max 16 
* IOPS
    * Min 100 & max 64 000
* Ratio
    * 50:1 - between IOPS & volume size
* To get max IOPS (64 000)
    * Min: 1280 GB as size


[<img src="https://i.imgur.com/znbCD94.png">](https://i.imgur.com/znbCD94.png)
[<img src="https://i.imgur.com/2VZ7vv6.png">](https://i.imgur.com/2VZ7vv6.png)
[<img src="https://i.imgur.com/6I2PLGn.png">](https://i.imgur.com/6I2PLGn.png)

----------------

### ST1
* Streaming workloads requiring consistent, fast throughput at a low price
* Big data, Data warehouse, Log processing
* Apache Kafka
* Cannot be a boot volume
* Size 
  * Min 500 GB & max 16 TB
* Max IOPS is 500
* Max throughput of 500 MiB/s - can burst

[<img src="https://i.imgur.com/MGR4DsE.png">](https://i.imgur.com/MGR4DsE.png)
[<img src="https://i.imgur.com/Ear0jX0.png">](https://i.imgur.com/Ear0jX0.png)
[<img src="https://i.imgur.com/aoU7Lu7.png">](https://i.imgur.com/aoU7Lu7.png)
