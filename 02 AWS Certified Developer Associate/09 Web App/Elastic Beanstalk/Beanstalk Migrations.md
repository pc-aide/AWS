# Beanstalk Migrations

## Acronym
* LB - Load Balancer
* ELB - Elastic Load Balancer
* ALB - Application Load Balancer
* NLB - Network Load Balancer
* CLB - Classic Load Balancer
* RDS - Relational Database Service
* DB - database
* PRD - Production
* EB - Elastic Beanstalk

## Doc

## Beanstalk Migration: LB
* After creating an Beanstalk environment, **you can't change the ELB type** (only the configuration)
    * Example: Beanstalk.**CLB** cannot to upgrade for ALB or NLB
* To migrate:
    1) Create a new environment with same configuration except LB (can't clone) - you can use the clone feature here, so create manually the same cfg
    2) Deploy your application into the new environment
    3) Perform a CNAME swap or Route 53 update
    
### Diagram
[<img src="https://i.imgur.com/9pzhBdM.png">](https://i.imgur.com/9pzhBdM.png)

---

## RDS with Beanstalk
* RDS can be provisioned with Beanstalk, which is great for **dev**/**test**
* This is not great for **prod** as the db lifecycle is tied to the beanstalk environment lifecycle
* The best for **prd** is to separately create an RDS db & provide our EB application with the connection string

### Diagram
[<img src="https://i.imgur.com/KZ10ywM.png">](https://i.imgur.com/KZ10ywM.png)

---

## EB Migration: Decouple RDS
1) Create a snapshot of RDS DB (as a safeguard)
2) Go to the RDS console & protect the RDS db from deletion
3) Create a new EB environment, without RDS, point your application to existing RDS
4) Perform a CNAME swap (blue/green) or Route 53 update, confirm working
5) Terminate the old environment (RDS won't be deleted)
6) Delete CloudFormation stack (in DELETE_FAILED state)

### Diagram
[<img src="https://i.imgur.com/U5jf7jx.png">](https://i.imgur.com/U5jf7jx.png)
[<img src="https://i.imgur.com/DD4mox4.png">](https://i.imgur.com/DD4mox4.png)
