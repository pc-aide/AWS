# Redshift

## Doc
* [Amazon Redshift Spectrum Extends Data Warehousing Out to Exabytes—No Loading Required](https://aws.amazon.com/blogs/big-data/amazon-redshift-spectrum-extends-data-warehousing-out-to-exabytes-no-loading-required/)

## Acronym
* OLTP - OnLine Transaction Processing
* DR - Disaster Recovery
* KMS - Key Management Service
* IAM - Identity & Access Management
* AZ - Availability Zone
* BI - Business Intelligence
* RDS - Relational Database Service
* OLAP - OnLine Analytical Processing
* PB - PeraBytes
* MPP - Massively Parallel Query Execution
* DMS - Database Migration Service

## Intro
* Redshift is based on PostgreSQL, but **it's not use for OLTP - RDS mush better choice for this**
* It's **OLAP** (analytics & **data warehousing**)
* 10x better performance than other data warehouses, scale to PBs of data
* **Columnar** storage of data (instead of row based)
* Massively Parallel Query Execution (MPP)
* Pay as you go based on the instances provisoned
  * it's not serverless
* Has a SQL interface for performing the queries
* BI tools such as AWS uicksight or Tableau integrate with it
* Data is loaded from **S3, Kinesis Firehose, DynamoDB, DMS**...
* From 1 node to 128 nodes, up to 160GB of space per node
* Can provision multiple nodes, but it's not Multi-AZ
* two of type of Readshift
  1) **Leader node**:
    * for query planning, results aggregation
  2) **Compute node:**
    * for performing the queries, send results to leader
* Backup & Restore, Security VPC/IAM/KMS, Monitoring
* Redshift Enhanced VPC Routing: COPY/UNLOAD goes through VPC
* Redshift is **provisoned**, sot it's worth it when you have a sustained usage (use Athena if the queries are sporadic instead)

---

## Snaptshots & DR
* Snaptshots are point-in-time backups of a cluster, stored internally in S3
* Snapshots are incremental (only what has changed is saved)
* You can restore a snapshot into a **new cluster**
* two of kinds of snapshots:
  1) **Automated:**
    * every 8 hours, every 5GB, or a schedule. Set retention
  2) **Manual:**
    * snapshot is retained until you delete it
* You can configure Redshift to automatically copy snapshots (automated or manual) of a cluster to another AWS Region

---

## Spectrum
* Query data that is already in S3 without loading it
* **Must have a Redshift cluster available to start the query**
* The query is then submitted to thousands of Redshift Spectrum nodes

### Diagram
[<img src="https://i.imgur.com/dFSnybE.png">](https://i.imgur.com/dFSnybE.png)
