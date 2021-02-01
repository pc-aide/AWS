# AWS DMS

## Acronym
* CDS - Change Data Capture
* DML - Data Manipulation Language
* DMS - Database Migration Service

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
  * On-Premise & 

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
