# Three Tier Architecture

## Doc
* [WordPress: Best Practices on AWS](https://aws.amazon.com/blogs/architecture/wordpress-best-practices-on-aws/)

## Acronym
* LAMP - Linux, Apache, MySQL, PHP/Perl/Python
* DB - Database
* RDS - Relationnal Database Service
* EBS - Elastic Block Store

## Introduction
[<img src="https://i.imgur.com/TapLfGC.png">](https://i.imgur.com/TapLfGC.png)

---

## LAMP Stack on EC2
* Linux: OS for EC2 instances
* Apache: Web Server that run on Linxu (EC2)
* MySQL: db on RDS
* PHP: Application logic (running on EC2)
* Can add Redis/Memcached (**ElastiCache**) to include a caching tech
* To store local application data & software: **EBS** drive (root)

---

## WordPress on AWS
[<img src="https://i.imgur.com/TVfrCH2.png">](https://i.imgur.com/TVfrCH2.png)
[<img src="https://i.imgur.com/mffU6Ff.png">](https://i.imgur.com/mffU6Ff.png)
