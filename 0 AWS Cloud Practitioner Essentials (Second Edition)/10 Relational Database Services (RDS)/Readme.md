# Relational Database Services (RDS)

## Acronym
* RDS - Relational Database Service
* OS - Operating System
* DB - Database
* VPC - Virtual Private Cloud
* prd - production

## Doc
* [Amazon Relational Database Service (RDS)](https://aws.amazon.com/rds/)

## Video 
* [Amazon RDS Service Introduction | 5m](https://www.aws.training/Details/Video?id=36900)

## Challenges of Relational Databases
* Server maintenance & energy footprint
* Software install & patches
* Database backups & high availability
* Limits on scalability
* Data security
* OS install & patches

## Introduction Amazon RDS
* **Amazon RSS** is a managed service that sets up & operates a relational database in the 
  cloud
  
  [<img src="https://i.imgur.com/BN32DhT.png">](https://i.imgur.com/BN32DhT.png)
  
* You manage
    * Application optimization
    
* AWS manage
    * OS installation & patches
    * Database software install & pathces
    * Databases backups
    * High availability
    * Scaling
    * Power & rack & stack
    * Server mantenance
    
## RDS DB Instances
[<img src="https://i.imgur.com/8G5961o.png">](https://i.imgur.com/8G5961o.png)

## RDS in your VPC
[<img src="https://i.imgur.com/551POyH.png">](https://i.imgur.com/551POyH.png)

## High Availability with Multi-AZ
[<img src="https://i.imgur.com/7e8nPbx.png">](https://i.imgur.com/7e8nPbx.png)
* Normal

[<img src="https://i.imgur.com/pya3L3k.png">](https://i.imgur.com/pya3L3k.png)
* If fail
    * Using rDS/DNS endpoint, you don't need to change anything in your application code
      to use the standy copy for failover
    * RDS also supports the cration of read replicas
    
## RDS Read Replicas
[<img src="https://i.imgur.com/mHC0V1q.png">](https://i.imgur.com/mHC0V1q.png)

* Asynchronous replication method used
* Offload read queries from the master DB instance
* Ideal for read-heavy database workloads
* Read replica can be promoted to Master if needed

## use Cases
* Web & Mobile Applications
    * High throughput
    * Massive storage scalability
    * High availability
* E-commerce Application
    * Low-cost database
    * Data security
    * Fully managed solution
* Mobile & Online Games
    * Rapidly grow capacity
    * Automatic scaling
    * Database monitoring
    
## RDS Benefits
* Highly scalable
* High performance
* Easy to administer
* Available & durable
* Secure & compliant

## Eg.
### AWS Console
* RDS

[<img src="https://i.imgur.com/mz0JUUN.png">](https://i.imgur.com/mz0JUUN.png)

## RDS for Oracle
### E.g
1) Clinet Oracle SQ Developer: Start page : 

[<img src="https://i.imgur.com/5pATC0V.png">](https://i.imgur.com/5pATC0V.png)

2) AWS Console RDS\Create Instance : 

[<img src="https://i.imgur.com/PFDZkTX.png">](https://i.imgur.com/PFDZkTX.png)

3) Select Engine\Oracle :

[<img src="https://i.imgur.com/AVhJieq.png">](https://i.imgur.com/AVhJieq.png)

4) Do you pla to use this DB for prd purposes? :

[<img src="https://i.imgur.com/H26FW6A.png">](https://i.imgur.com/H26FW6A.png)

5) Config adv settings :

[<img src="https://i.imgur.com/5keLAcS.png">](https://i.imgur.com/5keLAcS.png)
[<img src="https://i.imgur.com/ZqLj5nx.png">](https://i.imgur.com/ZqLj5nx.png)
[<img src="https://i.imgur.com/lnSr9Y2.png">](https://i.imgur.com/lnSr9Y2.png)

6) DB Instance (creating...) : 

[<img src="https://i.imgur.com/u92z2Hx.png">](https://i.imgur.com/u92z2Hx.png)

7) Security group\Inbound default port :

[<img src="https://i.imgur.com/iHjmGHl.png">](https://i.imgur.com/iHjmGHl.png)


8) Backing-up :

[<img src="https://i.imgur.com/wIUxcEd.png">](https://i.imgur.com/wIUxcEd.png)

9) Connections (Client) : 

[<img src="https://i.imgur.com/wsFffjf.png">](https://i.imgur.com/wsFffjf.png)
[<img src="https://i.imgur.com/rfOn23o.png">](https://i.imgur.com/rfOn23o.png)
