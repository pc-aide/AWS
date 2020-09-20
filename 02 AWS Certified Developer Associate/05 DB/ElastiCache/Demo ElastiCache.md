# Demo ElastiCache.md

## Acronym

## Doc
* [Amazon ElastiCache Documentation](https://docs.aws.amazon.com/elasticache/index.html)
* [Managing Your ElastiCache Clusters](https://docs.aws.amazon.com/AmazonElastiCache/latest/red-ug/Clusters.html)

## Create ElastiCache
### Redis
* Cluster engine: Redis
* Name: ElastiCacheRedis-01
* Engine version compatibility: 5.0.6
* Port: 6379
* Parameter group: default.redis5.0
* Node type: cache.t2.micro (for demo)
* Number of replicas: 0 (for demo)
* Advanced Redis settings:
    * Subnet group\Create new:
      * Name: SubnetElastiCacheRedis
      * Subnets: CheckBox -> ca-central-1a
* Create

[<img src="https://i.imgur.com/0ni989C.png">](https://i.imgur.com/0ni989C.png)

* When it'll be created, we can delete it & UncheckBox Backup

[<img src="https://i.imgur.com/rcKAQDD.png">](https://i.imgur.com/rcKAQDD.png)
[<img src="https://i.imgur.com/S6YdR2H.png">](https://i.imgur.com/S6YdR2H.png)
