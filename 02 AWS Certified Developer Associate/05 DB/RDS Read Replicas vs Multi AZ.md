# RDS Read Replicas vs Multi AZ

## Acronym
* AZ - Avalability Zone
* DB - Database
* DR - Disaster Recovery

## Doc
*

## RDS Read Replicas for read scalability
* Up to 5 Read Replicas
* Within AZ, Cross AZ or Cross Region
* Replication is **ASYNC**, so reads are eventually consistent
* Replicas can be promoted to their own dB
* Applications must update the connection string to leverage read replicas

### Topology
[<img src="https://i.imgur.com/RMkjdcr.png">](https://i.imgur.com/RMkjdcr.png)

---

## RDS Read Replicas - Use Case
* You have a production db that is taking on normal load
* You want ot run a reporting application to run some analytics
* You create Read Replica to run the new workload there
* The production application is unaffected
* Read replicas are used for SELECT (=read) only kind of statements
    * (no INSERT, UPDATE, DELETE)

### Topology
[<img src="https://i.imgur.com/aHvBbIY.png">](https://i.imgur.com/aHvBbIY.png)

---

## RDS Read Replicas - Network Cost
* In AWS there's a network cost when data goes from one AZ to another
* To reduce the cost, you can have your Read Replicas in the same AZ

### Toplogy
[<img src="https://i.imgur.com/0MFgfTA.png">](https://i.imgur.com/0MFgfTA.png)

---

## RDS Multi AZ (DR)
* SYNC replication
* One DSNS name - automatic app failover to standby
* Increase **availability**
* Failover in case of loss of AZ, loss of network, instance or storage failure
* No manual intervention in apps
* Not used for scaling
* <ins>Note:</ins> The Read Rplicas be setup as Multi AZ for DR

### Topology
[<img src="https://i.imgur.com/CP9mjbU.png">](https://i.imgur.com/CP9mjbU.png)
