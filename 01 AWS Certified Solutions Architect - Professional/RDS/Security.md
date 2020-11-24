# Security

## Acronym
* RDS - Relational Database Service
* EBS - Elastic Block Store
* TDE - Transparent Data Encryption
* IAM - Identity & Access Management

## Intro
* KMS encryption at rest for underlying EBS volumes/snapshots
* TDE for Oracle & SQS Server
* SSL encryption to RDS is possible for all DB (in-flight)
* IAM authentication for MySQL & PostgreSQL
* Authorization still happens within RDS (not in IAM)
* Can copy an un-encrypted RDS snapshot into an encrypted one
* CloudTrail cannot be used to track queries made within RDS
