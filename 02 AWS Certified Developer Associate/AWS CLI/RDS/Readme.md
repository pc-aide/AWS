# RDS

## Acronym
* SG - Security Group

## File
1. ~/.my.cnf
    a. mysql --print-defaults
````bash
[client]
user=
password=
host=
````
[<img src="https://i.imgur.com/YO2mzUT.png">](https://i.imgur.com/YO2mzUT.png)


## Switchs
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

### 02 Vertical scaling (scalling up)
````bash
# --apply-immediately (optional)
aws rds modify-db-instance \
--db-instance-identifier demo-rds-db \
--db-instance-class db.t2.medium
````
[<img src="https://i.imgur.com/NbxSRGu.png">](https://i.imgur.com/NbxSRGu.png)
[<img src="https://i.imgur.com/IpcBptz.png">](https://i.imgur.com/IpcBptz.png)
[<img src="https://i.imgur.com/4WZ6hUE.png">](https://i.imgur.com/4WZ6hUE.png)

* cheating for new instance-type with maintenance set up

[<img src="https://i.imgur.com/XQFxzFV.png">](https://i.imgur.com/XQFxzFV.png)

* Modifying...

[<img src="https://i.imgur.com/0766vMJ.png">](https://i.imgur.com/0766vMJ.png)

* if you choose to long time for maintenance 

[<img src="https://i.imgur.com/WDmqGz8.png">](https://i.imgur.com/WDmqGz8.png)

* after  modifying (~8 min):

[<img src="https://i.imgur.com/kjowRS9.png">](https://i.imgur.com/kjowRS9.png)
[<img src="https://i.imgur.com/HaGN134.png">](https://i.imgur.com/HaGN134.png)


### 03 Scalling up (storage)
````bash
## Ratio: storage vs iops:
# Size(gp2) = 1..33 -> 100 IOPS
# Size(gp2) = 34 -> 102 IPS
# io1 -> ratio 50:1
````

[<img src="https://i.imgur.com/U1S0w7p.png">](https://i.imgur.com/U1S0w7p.png)
