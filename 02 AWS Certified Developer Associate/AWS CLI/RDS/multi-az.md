# mutli-az

## Examples
### 01 multi-az
````bash
aws rds create-db-instance \
--db-instance-class db.t2.micro \
--allocated-storage 10 \
--db-instance-identifier multi-az-rds-mysql-db \
--engine mysql \
--master-username <value> \
--master-user-password <value> \
--multi-az \
--vpc-security-group-ids <groupID>
````
[<img src="https://i.imgur.com/ttRABeR.png">](https://i.imgur.com/ttRABeR.png)
[<img src="https://i.imgur.com/On2xQdJ.png">](https://i.imgur.com/On2xQdJ.png)
