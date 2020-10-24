# iam-db-authentication

## Acronym
* IAM - Idenity & Access Management

## Examples
### 01 Enabled iam-db-auth
````bash
aws rds modify-db-instance \
--db-instance-identifier multi-az-rds-mysql-db \
--enable-iam-database-authentication \
--apply-immediately
````
[<img src="https://i.imgur.com/1077g2q.png">](https://i.imgur.com/1077g2q.png)
[<img src="https://i.imgur.com/00ecfx6.png">](https://i.imgur.com/00ecfx6.png)
[<img src="https://i.imgur.com/MxEfuuJ.png">](https://i.imgur.com/MxEfuuJ.png)
