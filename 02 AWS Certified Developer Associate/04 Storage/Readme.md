# 04 Storage

## Doc
* [Making an Amazon EBS volume available for use on Linux](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ebs-using-volumes.html)

## Acronym
* EBS - Elastic Block store
* EC2 - Elatic Compute Cloud
* AZ - Avalability Zone
* GP2 SSD - General purpose SSD
* IO1 SSD- Highest-performance SSD

## What's an EBS Volume?
* A EC2 machine loses its root volume (main drive) when it's manually terminated
* Unexpected terminations might happen from time to time (AWS would email you)
* Sometimes, you need a way to store your instance data somehwhere
* An **EBS** volume is a**network** drive you can attach to your instances while they run
* It allows your instances to persist data 

## EBS Volume
* It's a network drive (i.e. not a physical drive)
    * It uses the network to cummunicate the instance, which means there might be a bit of latency
    * It can be detached from an EC2 instance & attached to another one quickly
* It's locked to an AZ
    * An EBS Volume in us-east-1a cannot be attached to us-east-1b
    * To move a volume across, your first need to snapshot it
* Have a provisioned capacity (size in GBs, & IOPS)
    * You get billed for all the provsioned capacity
    * You can increase the capacity of the driver over time
    
## Topology
[<img src="https://i.imgur.com/z78WY2K.png">](https://i.imgur.com/z78WY2K.png)

## EBS Volume Types
* EBS Volumes come in 4 types
  * **GP2 (SSD)**: General purpose SSD volume that balances price & performance for a wide variety of workloads
  * **IO1 (SSD)**: Highest-performance SSD volume for mission-critical low-latency or high-throughput workloads
  * **ST1 (HDD)**: Low cost HDD volume designed for frequently accessed, throughput-intensive workloads
  * **SC1 (HDD)**: Lowest cost HDD volume designed for less frequently accessed workloads
* EBS Volumes are chareacterized in Size | Throughput | IOPS (I/O Ops Per Sec)
* When in doubt always consult the AWS documentation - it's good
* Only GP2 & IO1 can be used as boot volumes

## Overview in AWS
[<img src="https://i.imgur.com/3lHU89c.png">](https://i.imgur.com/3lHU89c.png)
