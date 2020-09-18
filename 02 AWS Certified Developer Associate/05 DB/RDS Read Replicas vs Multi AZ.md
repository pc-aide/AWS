# RDS Read Replicas vs Multi AZ

## Acronym
* AZ - Avalability Zone
* DB - Database

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
