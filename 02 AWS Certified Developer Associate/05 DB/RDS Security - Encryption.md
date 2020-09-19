# RDS Security - Encryption

## Doc

## Acronym
* TDE - Transparent Data Encryption 
* SSL - Secure Sockets Layer
* db - database
* IAM - Identity & access management
* RDS - Relational database service
* SG - Security Group

## Introduction
* The encryption option - it's not avalable when you create a new db (template free tier)
* At rest encryption 
    * Possibility to encrypt the master & read replicas with AWS KMS-AES-256 encryption
    * Encryption has to be defined at luanch time
    * If the master is not encrypted, the read replicas <ins>cannot</ins> be encrypted 
    * TDE available for Oracle & SQL Server
* In-flight encryption
  * SSL certificates to encrypt data to RDS in flight
  * Provide SSL options with trust certifcate when connecting to db
  * To <ins>enforce</ins> SSL:
      * PostgreSQL: rds:force_ssl=1 in the AWS RDS Console (Parameter Groups)
      * MySQL: Within the DB:
        * GRANT USAGE ON *.* TO 'mysqluser'@'%' REUIRE SSL;

### Topology
[<img src="https://i.imgur.com/zXQuroj.png">](https://i.imgur.com/zXQuroj.png)

---

## RDS Encryption Operations
* Encrypting RDS backups
    * Snapshots of un-encrypted RDS DBs are un-encrypted
    * Snaptshot of encrypted RDS DBs are encrypted
    * Can copy a snapshot into an encrypted one
* To encrypt a un-encrypted RDS db:
    * Create a snapshot of the un-encrypted db
    * Copy the snapshot & enable encryption for the snapshot
    * Restore the db from the encrypted snapshot
    * Migrate applications to the new db, & delete the old db
    
---

## RDS Security - Network & IAM
* Network Security
    * RDS DBs are usally deployed within a private subnet, not in a public one
    * RDS security works by leveraging SGs (the same concept as for EC2 instances) - it controls which IP / SG
      can **communicate** with RDS
* Access Management
    * IAM policies help control who can **manage** RDS (through the RDS API)
    * Traditional UserName & Password can be used to **login into** the db
    * IAM-based authentication can be used to login into RDS MySQL & PostgreSQL
    
---

## RDS - IAM Authentication
* IAM db authentication works with **MySQL & PostgreSQL**
* You don't need a password, just an authentication toke obtained through IAM & RDS API calls
* Auth toke has a lifetime of 15 minutes
* Benefits:
    * Netowrk IN/OUT must be enecrypted using SSL
    * IAM to centrally manage users instead of DB
    * Can leverage IAM Roles & EC2 Instance profiles for easy integration

### Topology
[<img src="https://i.imgur.com/cPynUFU.png">](https://i.imgur.com/cPynUFU.png)

---

## RDS Security - Summary
* Encryption at rest:
    * Is done only when you first create the DB instance
    * Or: unencrypted DB => snapshot => copy snapshot as encrypted => create DB from snapshot
* Your responsibility:
    * Check the ports / IP / SG inbound rules in DB's SG
    * In-db user creation & permissions or manage through IAM
    * Creating a db with or without public access
    * Ensure parameter groups of DB is configured to only allow SSL connections
* AWS responsibility:
    * No SSH access
    * No manual DB patching
    * No manual OS patching
    * No way to audit the underlying instance
