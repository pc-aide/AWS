# Cache Deployment Options.md

## Table
|                | Memcached | Redis: Single<br>Node | Redis: Cluster<br>Mode Disabled | Redis: Cluster |
| -------------- | --------- | --------------------- | ------------------------------- | -------------- |
| Backup/Restore | No        | Yes                   | Yes                             | Yes            |
| Replication    | No        | No                    | Yes                             | Yes            |
| Sharding       | Yes       | No                    | No                              | Yes            |
