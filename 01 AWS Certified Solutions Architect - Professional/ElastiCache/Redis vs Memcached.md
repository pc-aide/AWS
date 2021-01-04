# Redis vs Memcached

## Table
|Redis                      |Memcached               |
|---------------------------|------------------------|
|Complex data types         |Simplest model possible |
|Backup & restore           |You need large nodes    |
|Sorted sets                | scale out or in (raise/shrink cacche) |
|Publisher/Subscriber model |cache objects |


---

## Cache Deployment Options
* Memcached Cluster
* Redis Single Node
* Redis Cluster with Cluster Mode Disabled
* Redis Cluster
