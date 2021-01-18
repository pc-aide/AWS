# Amazon EMR

## Acronym
* EMR - Elastic MapReduce
* AZ - Availability Zone
* EBS - Elastic Block Store
* CW - CloudWatch

## Intro
* EMR helps creating **Hadoop clusters (Big Data**) & **Apache Spark** to analyze & process vast amount of data
* Migrate On-premise your Hadoop cluster to AWS (for big compagny)
* The custers can be made of hundreds of EC2 instances
* Also support Apache Spark, HBase, Presto, Flink...
* EMR takes care of all the provisoning & configuration of EC2
* Auto-scaling with CW
* <ins>Use cases:</ins>
  * data processing, machine learning, web indexing, big data...
  
---

## Integrations
[<img src="https://i.imgur.com/4ZmrbZs.png">](https://i.imgur.com/4ZmrbZs.png)

---

## Node types & purchasing
* **Master Node**: Manage the cluster, coordinate, manage health
* **Core Node**: Run tasks & store data
* **Task Node (optional**): Just to run tasks
* **Purchasing options**:
  1) On-demand: reliable, predictable, won't be terminated
  2) Reserved (min 1 year): cost savings (EMR will automatically use if available)
  3) Spot Instances: cheaper, can be terminated, less reliable
* Can have long-running cluster, or transient (temporary) cluster
* One big cluster vs many samller one? Long running vs transient?

--- 

## Instance Configuration
* **Uniform instance groups**: select a single instance type & pruchasing option for each node (has auto scaling)
* **Instance fleet**: select target capacity, mix instance types & purchasing options (no Auto Scaling)

### IMG
[<img src="https://i.imgur.com/UUNC4Qx.png">](https://i.imgur.com/UUNC4Qx.png)
