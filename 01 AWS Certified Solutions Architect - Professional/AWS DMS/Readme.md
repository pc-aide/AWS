# AWS DMS

## Acronym
* BLOB - Binary Large OBject
* CDC - Change Data Capture
* DML - Data Manipulation Language
* DMS - Database Migration Service
* SCT - Schema Conversion Tool
* TB - TeraByte
* TDE - Transparent Data Encryption

## Intro
* Quickly & securely migrate database to AWS, resilient, self healing
* The source database remains available during the migration
* Supports:
  * Homogeneous migrations: ex Oracle db to Oracle other db
  * Heterogeneous migrations: ex Microsoft SQL Server to Aurora
* Continuous Data Replication using CDC
* You must create an EC2 instance to perform the replication tasks

### Diagram
[<img src="https://i.imgur.com/Y99AvGl.png">](https://i.imgur.com/Y99AvGl.png)

---

## DMS Sources & Targets
* <ins>Sources:</ins>
  * On-Premise & EC2 instances databases: Oracle, MS SQL Server, MySQL, MariaDB, PostgreSQL, MongoDB, SAP, DB2
  * Azure: Azure SQL Database 
  * Amazon RDS : all incuding Aurora
  * Amazon S3
* <ins>Targets:</ins>
  * On-Premise & EC2 instances databases: Oracle, MS SQL Server, MySQL, MariaDB, PostgreSQL, SAP
  * Amazon RDS
  * Amazon Redshift
  * Amazon DynamoDB
  * Amazon S3
  * ElasticSearch Service
  * Kinesis Data Streams
  * DocumentDB
  
---

## AWS SCT
* Convert your Database's Schema from one engine to another
* Example OLTP: (SQL Server or Oracle) to MySQL, PostgreSQL, Aurora
* Example OLAP: (Teradata or Oracle) to Amazon Redshift
* You  don't need to use SCT if your are migrating  the same DB engine
  * Ex: On-Premise PostgreSQL => RDS PostgreSQL
  * The DB engine is still PostgreSQL (RDS is the platform)
  
### Diagram
[<img src="https://i.imgur.com/QSHHXz2.png">](https://i.imgur.com/QSHHXz2.png)

---

## DMS - Good things to know
* Works over VPC Perring, VPN (site to site, software), Direct Connect
* Supports Full Load + CDC, or CDC only
* Oracle:
  * Source: Supports TDE for the source using "BinaryReader"
  * Target: Supports BLOBs in tables that have a primary key, & TDE
* ElasticSearch:
  * Source: does not exist
  * Target: possible to migrate to DMS from a relational database
  * Therefore DMS cannot be used to replicate ElasticSearch data
  
---

## Snowball + DMS
* Larger data migrations can include many TBs of information
* Can be limited due to network badwidth or size of data
* AWS DMS can use Snowball Edge & Amazon S3 to speed up migration
* Following stages:
  1. You use the AWS SCT to extract the data locally & move it to an Edge device
  2. You ship the Edge device or devices back to AWS
  3. After AWS receives your shipment, the Edge device automatically loads its data into an Amazon S3 bucket
  4. AWS DMS takes the files and migrates the data to the target data store. If you are using CDC, those updates are written to the Amazon S3 bucket & then applied to the target data store

---

## Factors Impacting DMS Performance
* Resource availability on the source
* Available network throughput
* Resource capacity of the replication server
* Ability of the target to ingest changes
* Type & distribution of source data
* Number of objects to be migrated

---

## Best Practices for DMS Performance
* Control tables migrating in parallel
* For full load tasks, drop:
  * Primary key indexes
  * Secondary indexes
  * Referential integrity constraints
  * DML triggers
* Disable backups & transaction logging
* Use multiple tasks
* Consider batch optimized apply option
* Right size the replication instance
* Reduce load on the source database
* Task log
