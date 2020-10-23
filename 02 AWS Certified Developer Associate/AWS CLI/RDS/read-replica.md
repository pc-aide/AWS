# read-replica

## Switch
* aws rds create-db-instance-read-replica help

## Examples
### 01 create read replicas
````bash
# Read replicas (horizontal scalling)
# db-instance-identifier must not exist !
aws rds create-db-instance-read-replica \
--db-instance-identifier demo-rds-db-replica \
--source-db-instance-identifier demo-rds-db
````
[<img src="https://i.imgur.com/qbPUJbt.png">](https://i.imgur.com/qbPUJbt.png)
[<img src="https://i.imgur.com/2LWd1J6.png">](https://i.imgur.com/2LWd1J6.png)
[<img src="https://i.imgur.com/MFRS4g3.png">](https://i.imgur.com/MFRS4g3.png)
