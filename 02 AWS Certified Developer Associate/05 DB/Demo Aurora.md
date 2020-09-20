# Demo Aurora

## Doc
* [Creating an Amazon Aurora DB Cluster](https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/Aurora.CreateInstance.html)
* [Using Amazon Aurora Serverless](https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/aurora-serverless.html)
* [Working with Parallel Query for Amazon Aurora MySQ](https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/aurora-mysql-parallel-query.html)
* [Using Amazon Aurora Global Databases](https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/aurora-global-database.html#aurora-global-database-attaching)
* [Single-Master Replication with Amazon Aurora MySQL](https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/AuroraMySQL.Replication.html)
* [Working with Aurora Multi-Master Clusters](https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/aurora-multi-master.html)
* [DB Instance Classes](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Concepts.DBInstanceClass.html)

## Acronym
* DB - database
* SG - Security Group
* cfg - Configuration

## Create db
* Engine options: Amazon Aurora
* Editon: MySQL
* Capacity type: Provisioned
* Version: Aurora (MySQL 5.7) 2.07.2
* Template: Dev/Test
* Settings
    * DB cluster identifier: ca-db-01
    * Cred: UserName&Pwd
* DB instance size
  * RadioButton: Bustable  classes
    * db.t2.smal
* Availability & durability : default (Create a Aurora...)
* Connectivity
    * VPC : default
    * Subnet: default
    * Public access: No
    * SG: default - (can change when it'll be created)
    * Port: default (3306)
* Additional cfg
    * DB options
      * Initial  db name: ca_AuraDB_01
* Maintenance
  * Uncheckbox: Deletion protection (for demo)
* Create db

[<img src="https://i.imgur.com/7Pe8UC2.png">](https://i.imgur.com/7Pe8UC2.png)
[<img src="https://i.imgur.com/Vs2lnvX.png">](https://i.imgur.com/Vs2lnvX.png)
[<img src="https://i.imgur.com/GCNmsC2.png">](https://i.imgur.com/GCNmsC2.png)
[<img src="https://i.imgur.com/OLXy7x6.png">](https://i.imgur.com/OLXy7x6.png)
[<img src="https://i.imgur.com/sD6eT80.png">](https://i.imgur.com/sD6eT80.png)

### Overview new Aurora
* Endpoint: 2x:
    * 1 - \<id\> - writer endpoint
    * 2 - ro-... - reader-only endpoint

[<img src="https://i.imgur.com/uYHyAwS.png">](https://i.imgur.com/uYHyAwS.png)
[<img src="https://i.imgur.com/zyLt3u3.png">](https://i.imgur.com/zyLt3u3.png)

### Auto scaling
[<img src="https://i.imgur.com/3ezVwfZ.png">](https://i.imgur.com/3ezVwfZ.png)
[<img src="https://i.imgur.com/l344DD1.png">](https://i.imgur.com/l344DD1.png)

* When done for overview - juste delete our Aurora (because $$$)
