# read-replica

## Switch
* aws rds create-db-instance-read-replica help

## Examples
### 01 create read replicas
````bash
# Read replicas (horizontal scalling)
aws rds create-db-instance-read-replica \
--instance-identifier demo-rds-db \
--source-db-instance-identifier <value>
````
[<img src="https://i.imgur.com/Gh60zyS.png">](https://i.imgur.com/Gh60zyS.png)
[<img src="https://i.imgur.com/ukiGSI8.png">](https://i.imgur.com/ukiGSI8.png)
