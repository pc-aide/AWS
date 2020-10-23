# RDS

## Acronym
* SG - Security Group

## Swithc
* aws rds create-db-instance help

## Examples
### 01 Create db
````bash
aws rds create-db-instance \
--db-instance-class db.t2.micro \
--allocated-storage 10 \
--db-instance-identifier demo-rds-db \
--engine mysql \
--master-username admin \
--master-user-password "String"
````
[<img src="https://i.imgur.com/64FUgU8.png">](https://i.imgur.com/64FUgU8.png)
[<img src="https://i.imgur.com/Xl5T7EB.png">](https://i.imgur.com/Xl5T7EB.png)
[<img src="https://i.imgur.com/aeMcfab.png">](https://i.imgur.com/aeMcfab.png)
[<img src="https://i.imgur.com/GmhlNwk.png">](https://i.imgur.com/GmhlNwk.png)

* SG:

[<img src="https://i.imgur.com/6OUGCFf.png">](https://i.imgur.com/6OUGCFf.png)

* Replication:

[<img src="https://i.imgur.com/2RE6Vfr.png">](https://i.imgur.com/2RE6Vfr.png)
