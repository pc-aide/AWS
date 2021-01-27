# EC2

## Acronym
* AZ - Availability Zone
* VM - Virtual Machine
* HA - High Availability
* HDFS - Hadoop Distributed File System 

## Doc
* [ec2 instances info](https://www.ec2instances.info/)

## EC2 Instance Types - Main ones
* **R**: applications that needs a lot of **RAM** - in-memory caches
* **C**: applications that needs good **CPU** - compute/database
* **M**: applications that are balanced (think "**medium**") - general/web app
* **I**: applications that need good local **I/O** (instance storage) - databases
* **G**: applications that need a **GPU** - video rendering/machine learning
* **T2/T3**: **burstable** instances (up to a capacity)
* T2/T3: unlimited: unlimited burst

---

## Placement Groups
* Control the EC2 Instance placement strategy using placement groups
* Group Strategies:
  * **Cluster** - cluters instances into a low-latency group in a single AZ
  * **Spead** - spreads instances across underlying hardware (max 7 instances per group per AZ) - critical applications
  * **Partition** - speads instances across many different partitions (which rely on different sets of racks) within an AZ. Scale to 100s of EC2 instances per group (Hadoop, Cassandre, Kafka)
* You can move an instance into or out of a placement group
  * Your first need to **stop** it
  * You then need to use the CLI (modify-instance-placement)
  * You can then **start** your instance

---

## Placement Groups Cluster
* Pros:
  * Great network (10 Gbps bandwidth between instances)
* Cons:
  * If the rack fails, all instances fails at the same time (because same AZ for all EC2 instances)
* Note: choose than instance type that has **Enhanced Networking**
* Use case:
  * Big Data job that needs to complete fast
  * Application that needs extremely low latency & high network throughput

### Diagram
[<img src="https://i.imgur.com/hkRht7X.png">](https://i.imgur.com/hkRht7X.png)

---

## Placement Groups Spread
* Pros:
  * Can span across AZ
  * Reduced risk is simultaneous failure
  * EC2 Instances are on different physical hardware
* Cons:
  * Limited to 7 instances per AZ per placement group
* Use case:
  * Application that needs to maximize HA
  * Critical Applications where each instance must be isolated from failure from each other

### Diagram
[<img src="https://i.imgur.com/iX7G36z.png">](https://i.imgur.com/iX7G36z.png)

---

## Placement Groups Partion
* Up to 7 partitions per AZ
* Up to 100s of EC2 instances
* The instances in a partitions do not share racks with the instances in the other partitions
* A partition failure can affect many EC2 but won't affect other partitions
* EC2 instances get access to the partition information as metadata
* <ins>Use cases:</ins>
  * HDFS, HBase, Cassandra, Kafka

### Diagram
[<img src="https://i.imgur.com/VR1Gf10.png">](https://i.imgur.com/VR1Gf10.png)

---

## EC2 Instance Launch Types
1) **On Demand** Instances: short workload, predictable pricing, reliable
  * a bit more expensive
2) **Spot** Instances: short workloads, for cheap, can lose instances (not reliable)
3) **Reserved**: (MINIMUM 1 year)
   1) **Reserverd Instances**: log workloads
   2) **Convertible Reserved Instances**: log workloads with flexible instances
   3) **Scheduled Reserved Instances**: example - every Thursday between 3 & 6 pm
4) **Dedicated Instances**: no other customers will share your hardware
5) **Dedicated Hosts:** book an entire **physical server**, control instance placement
  * Great for **software licenses** that operate at the core, or CPU socket level
  * Can define **host affinity** so that instance reboots are kept on the same host
  
---

## EC2 included metrics
* <ins>CPU:</ins> CPU Utilization + Credit Usage/Balance
* <ins>Network:</ins> Network In/Out
* <ins>Status Check:</ins>
  * Instance status = check the EC2 VM
  * System status = check the underlying hardware
* <ins>Disk:</ins> Read/Write for Ops/Bytes (only for instance store)
* <ins>RAM is NOT included in the EC2 metrics</ins>

---

## EC2 Instance Recovery
* <ins>Status Check:</ins>
  * Instance status = check the EC2 VM
  * System status = check the underlying hardware
* **Recovery**: Same Private, Public, Elastic IP, metadata, placement group

### Diagram
[<img src="https://i.imgur.com/79cH2gI.png">](https://i.imgur.com/79cH2gI.png)
