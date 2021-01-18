# AWS DMS

## Acronym
* DML - Data Manipulation Language
* DMS - Database Migration Service

## Intro

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