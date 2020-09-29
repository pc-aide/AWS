# CloudFront

## Doc
* [CloudFront Infrastructure](https://aws.amazon.com/cloudfront/features/?nc=sn&loc=2)
* [list-cloudfront-ips](http://d7uri8nf7uskq.cloudfront.net/tools/list-cloudfront-ips)

## Acronym
* CDN - Content Delivery Network
* DDoS - Distribute Denial of Service
* WAF - Web Application Firewall
* OAI - Origin Access Identity
* ALB - Application Load Balancer
* DB - Database

## Intro
* CDN
* Improves read performance, content is cached at the edge
* **216** Point o fPresence globally (**edge locations**)
* DDoS protection, integration with Shield, AWS WAF
* Can expose external HTTPS & can talk to internal HTTPS backedns

### Map
* Edge locations: ~220 units
* Multiple Edge location: ~25 units
* Regional Edge caches: ~12 units

[<img src="https://i.imgur.com/qIWvyVa.png">](https://i.imgur.com/qIWvyVa.png)

* Ex: S3 (autralia) & an user (ca-central):

[<img src="https://i.imgur.com/yCivNH6.png">](https://i.imgur.com/yCivNH6.png)
[<img src="https://i.imgur.com/B1zChq8.png">](https://i.imgur.com/B1zChq8.png)

---

## CloudFront - Origin
* S3 bucket
    * For distributing files & caching them at the edge
    * Enhanced security with CloudFront **Origin Access Identity (OAI)**
    * CloudFront can be used as an ingress (to upload files to S3)
* Custom Origin (HTTP)
    * ALB
    * EC2 instance
    * S3 website (must first enable the bucket as a static S3 website)
    * Any HTTP backend you want
    
---

## CloudFront at a high level
* client
* Edge Location
* Origin
    * S3 or HTTP
    
### Diagram
[<img src="https://i.imgur.com/U8GcZ0X.png">](https://i.imgur.com/U8GcZ0X.png)

---

## CloudFront - S3 as an Origin
[<img src="https://i.imgur.com/g9T5c8L.png">](https://i.imgur.com/g9T5c8L.png)

---

## CloudFront - ALB or EC2 as an origin
[<img src="blob:https://imgur.com/08bdee05-5396-4eaa-9756-82136b79f8d8

### list-cloudfront-ips
````text
{"CLOUDFRONT_GLOBAL_IP_LIST": ["120.52.22.96/27", "205.251.249.0/24", "180.163.57.128/26", "204.246.168.0/22", "205.251.252.0/23", "54.192.0.0/16", "204.246.173.0/24", "54.230.200.0/21", "120.253.240.192/26", "116.129.226.128/26", "99.86.0.0/16", "205.251.200.0/21", "223.71.71.128/25", "13.32.0.0/15", "120.253.245.128/26", "13.224.0.0/14", "70.132.0.0/18", "210.51.40.0/24", "13.249.0.0/16", "205.251.208.0/20", "65.9.128.0/18", "58.254.138.0/25", "54.230.208.0/20", "116.129.226.0/25", "52.222.128.0/17", "64.252.128.0/18", "205.251.254.0/24", "54.230.224.0/19", "71.152.0.0/17", "216.137.32.0/19", "204.246.172.0/24", "120.52.39.128/27", "118.193.97.64/26", "223.71.71.96/27", "130.176.0.0/16", "54.240.128.0/18", "205.251.250.0/23", "180.163.57.0/25", "52.46.0.0/18", "223.71.11.0/27", "52.82.128.0/19", "54.230.0.0/17", "54.230.128.0/18", "54.239.128.0/18", "36.103.232.128/26", "52.84.0.0/15", "111.51.66.0/24", "143.204.0.0/16", "144.220.0.0/16", "120.52.153.192/26", "119.147.182.0/25", "120.232.236.0/25", "54.182.0.0/16", "58.254.138.128/26", "120.253.245.192/27", "54.239.192.0/19", "120.52.12.64/26", "99.84.0.0/16", "52.124.128.0/17", "204.246.164.0/22", "13.35.0.0/16", "204.246.174.0/23", "36.103.232.0/25", "119.147.182.128/26", "118.193.97.128/25", "120.232.236.128/26", "204.246.176.0/20", "65.8.0.0/16", "65.9.0.0/17", "120.253.241.160/27", "64.252.64.0/18"], "CLOUDFRONT_REGIONAL_EDGE_IP_LIST": ["13.113.196.64/26", "13.113.203.0/24", "52.199.127.192/26", "13.124.199.0/24", "3.35.130.128/25", "52.78.247.128/26", "13.233.177.192/26", "15.207.13.128/25", "15.207.213.128/25", "52.66.194.128/26", "13.228.69.0/24", "52.220.191.0/26", "13.210.67.128/26", "13.54.63.128/26", "99.79.169.0/24", "18.192.142.0/23", "35.158.136.0/24", "52.57.254.0/24", "13.48.32.0/24", "18.200.212.0/23", "52.212.248.0/26", "3.10.17.128/25", "3.11.53.0/24", "52.56.127.0/25", "15.188.184.0/24", "52.47.139.0/24", "18.229.220.192/26", "54.233.255.128/26", "3.231.2.0/25", "3.234.232.224/27", "3.236.169.192/26", "3.236.48.0/23", "34.195.252.0/24", "34.226.14.0/24", "13.59.250.0/26", "18.216.170.128/25", "3.128.93.0/24", "3.134.215.0/24", "52.15.127.128/26", "52.52.191.128/26", "34.216.51.0/25", "34.223.12.224/27", "34.223.80.192/26", "35.162.63.192/26", "35.167.191.128/26", "44.227.178.0/24", "44.234.108.128/25", "44.234.90.252/30"]}
````

---

## CloudFront Geo Restriction
* You can restrict who can access your distribution
    * **Whitelist**: Allow your users to access your content only if they're in one of the countries on a list of approved countries
    * **Blacklist**: Prevent your users from accessing your content if they're in one of the countries on a blacklist of banned countries
* The "country" is determined using a 3rd party Geo-IP db
* Use case: Copyright Laws to control access to content

---

## CloudFront vs S3 Cross Region Replication
* CloudFront:
    * Gobal Edge network
    * Files are cached for a TTL (maybe a day)
    * Great for atatic content that must be available everywhere
* S3 Cross Region Replication:
    * Must be setup for each region you want replication to happen
    * Files are updated in near real-time
    * Read only
    * Great for dynamic content that needs to be available at low-latency in few regions
