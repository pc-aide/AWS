# 05 DB

## Acronym
* DB - Database
* RDS - Relationel Database Service
* DR - Disaster Recovery
* AZ -Availability Zone

## Terminology
* NoSQL - a RDS it's not a NoQSL
  * DynamoDB, it's a NoSQL

## Doc
* [What is NoSQL?](https://aws.amazon.com/nosql/)

## RDS
### Introduction
* RDS stands for Realtional Database Service
* It's a managed DB service for DB use SQL as a query language
* It allows you to create db in the cloud that are managed by AWS 
  * Postgre
  * MysQL
  * MariaDB
  * Oracle
  * Microsoft SQL Server
  * Aurora (AWS Proprietary db)
  
### Advantage over using RDS versus DB on EC2
* RDS is a managed service (PaaS):
  * Automated provisioning, OS patching
  * Continuous backups & restaore to specific timestamp (Point in Time Restore)!
  * Monitoring dashboards
  * Read replicas for improved read performance
  * Multi AZ setup for DR
  * Maintenance windows for upgrades
  * Scaling capability (vertical & horizontal)
  * Storage backed by EBS (gp2 or io1)
* But you can't SSH into your instances

### Backups
* Backups are automatically enabled in RDS
* Automated backups:
  * Daily full backup of the db (during the maintenance windows)
  * Transaction logs are backed-kup by RDS every 5 minutes
  * => ability to restore to any point in time (from oldest backup to 5 minutes ago)
  * 7 days retention (can be increased to 35 days)
* DB Snapshots:
  * Manually triggered by the user
  * Retention of backup for as long as you want
    * e.g: 6 month at some point in time (retention)
