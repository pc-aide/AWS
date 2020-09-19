# Demo-RDS-MySQL.md

## Doc
* [Managing Capacity Automatically with Amazon RDS Storage Autoscaling](https://passwordsgenerator.net/)
* [High Availability (Multi-AZ) for Amazon RDS](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Concepts.MultiAZ.html)
* [Amazon Virtual Private Cloud VPCs and Amazon RDS](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_VPC.html)

## Tools
* [sqlectron - simple & lightweight SQL client desktop/terminal](https://sqlectron.github.io/)

## Acronym
* DB - database
* gp - General purpose
* cfg - configuration
* SG - Security Group

## Create db
### Engine
* MysQL
* Version: MySQL 8.0.20

### Template
* Free tier

### Setings
* DB instance identifier: ca-db-01
* Master username: admin
* Maaster pwd: 

### DB instance size
* db.t2.micro

### Storage
* GP SSD
* Allocated storage: 20
* Uncheckbox: Enable storage autocaling

### Connectivity
* VPC : default

#### Additional connectivity cfg
* Public acces : yes (only for demo - in prd we choose no)
* SG : default ([i can't see my other SG !?)](https://i.imgur.com/u1osbdp.png)
    * After the new db was created, now i can change for [SG](https://i.imgur.com/TTH55Th.png)
* AZ: No preference
* DB port: 3306

### Additional cfg
* Initale db name: CaDB01

### Backup
* CheckBox: Enable automatic backups (default)
* Backup retention period: 7 days

### Maintenance
* Checkbox : Enable auto minor version upgrade (default)

### Done
* create db
    * Creating database ca-db-01. 
      Your database might take a **few minutes** to launch.


[<img src="https://i.imgur.com/1QtTCVJ.png">](https://i.imgur.com/1QtTCVJ.png)
[<img src="https://i.imgur.com/9mqrm5l.png">](https://i.imgur.com/9mqrm5l.png)
[<img src="https://i.imgur.com/61W1Z22.png">](https://i.imgur.com/61W1Z22.png)
[<img src="https://i.imgur.com/CQUqNKy.png">](https://i.imgur.com/CQUqNKy.png)
[<img src="https://i.imgur.com/georGyr.png">](https://i.imgur.com/georGyr.png)

#### Instance action
* Stop
* Reboot
* Created read replica
* Promote read replica
* Take snapshot
* Restore to point in time
* Migrate snaphot

[<img src="https://i.imgur.com/TyLbFhy.png">](https://i.imgur.com/TyLbFhy.png)

---

## SQLElectron
* Add
    * Name: Ca-DB-MySQL-01
    * DB Type: MySQL
    * SlideOn: SSL
    * Server Address: \<Endpoint\>
    * Port: 3306
    * User: \<cred\>
    * Pws: idem
    * Test: Successfully connected
    * Save:
    * Connect:
    
[<img src="https://i.imgur.com/YnH3MNh.png">](https://i.imgur.com/YnH3MNh.png)

### My db
* No table

[<img src="https://i.imgur.com/nByBIOH.png">](https://i.imgur.com/nByBIOH.png)
