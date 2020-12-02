# ElastiCache

## Aronym
* RDS - Relational Database Service 
* HA - 
* AZ - Availability Zone

## Intro
* The same way RDS is to get managed Relational Database...
* ElastiCache is to get managed **Redis** or **Memcached**
* Caches are in-memory databases with realy high performance, low latency
* Helps reduce load off of databases for read intensive workloads
* Helps make your applicate stateless
* AWS takes care of OS maintenance/patching, optimizations, setup, configuration, monitoring, failure recovery & backups
* <ins>Using ElastiCache involves heavy application code changes</ins>

---

## Solution Architecture - DB Cache
* Applications queries ElastiCache, if not available, get from RDS & store in ElastiCache
* Helps relieve load in RDS
* Cache must have an invalidation strategy to make sure only the most current data is used in there

## Diagram
[<img src="https://i.imgur.com/z9fMGcc.png">](https://i.imgur.com/z9fMGcc.png)

---

## Solution Architecture - User Session Store
* User logs into any of the application
* The application writes the session data into ElastiCache
* The user hits another instance of our application
* The instance retrieves the data & the user is already logged in

### Diagram
[<img src="https://i.imgur.com/2BXryDC.png">](https://i.imgur.com/2BXryDC.png)

---

## Redis vs Memcached
* Redis:
  * Multi AZ with Auto-Failover
  * **Read replicas** to scale reads & have HA
