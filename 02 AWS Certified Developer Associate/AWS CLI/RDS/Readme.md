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

### 02 - Modify maintenance
````bash
# check up between your maintanance & backup - no overlap (example)
aws rds modify-db-instance \
--db-instance-identifier demo-rds-db \
--preferred-maintenance-window Sat:08:00-Sat:08:30
````
[<img src="https://i.imgur.com/eD6JU0o.png">](https://i.imgur.com/eD6JU0o.png)
[<img src="https://i.imgur.com/703cxLR.png">](https://i.imgur.com/703cxLR.png)
[<img src="https://i.imgur.com/1WtA7mR.png">](https://i.imgur.com/1WtA7mR.png)
