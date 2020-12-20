# Optimizing Cost

## Acronym
* S3 - Simple Storage Service
* RDS - Relational Database Service
* gp2 or gp3 - general purpose SSD v2 or v3 
* io1 - Provisioned IOPS
* sc1 - Cold HDD
* st1 - Throughput Optimized HDD
* IAM - Identity & Access Management
* IA - Infrequently Access
* SNS - Simple Notification Service
* SCP - Service Control Policy


## 5 Common Mistakes
1) EC2 Instance Type
2) EC2 Instance Size
3) EC2 Volumes & Snapshots
4) Zombine Instances
5) S3 Storage Class

---

## Instace Type
* General
  * e.g -> m5.24xlarge | $4.608/hr | - tips think about "m" lke medium (avg cpu = avg ram)
* Hardware Accelerated 
  * e.g -> p3dn.24xlarge | $31.212/hr
  
---

## Instance Size
* Right size instance for workload
* Gather metrics to determine size
* Don't pay for waht don't need
* Tenancy
  * **Dedicated host**
    * where you are the only customer on a given **physical machine**
  * Only for specific use cases
* Other AWS services have sizes
  * like RDS


| Instance size | vCPU | RAM (GiB) | Cost (hr) |
|---------------|------|-----------|-----------|
| m5.large      | 2    | 8         | $0.096    |
| m5.xlarge     | 4    | 16        | $0.192    |
| m5.2xlarge    | 8    | 32        | $0.384    |
| m5.4xlarge    | 16   | 64        | $0.768    |
| m5.8xlarge    | 32   | 128       | $1.536    |
| m5.12xlarge   | 48   | 192       | $2.304    |
| m5.16xlarge   | 64   | 256       | $3.072    |
| m5.24xlarge   | 96   | 384       | $4.608    |
| m5 dedicated host | | | $5.069 |

----

## Volumes & Snapshots
* Volume types
  * gp2 or gp3
  * magnitic
  * io1 or io3
  * sc1
* price by region
  * $25-$125/month -> 1TB
* Always Charged
  * Still pay for volumes even when EC2 instance is stopped
    * because you have provisioned
* Snapshots
  * Only provision what you need for EC2s
  * Delete when finished
  
---

## Zombie Instances
* No one knows what they are doing
* IAM permissions, tagging, multi-account management
* Clear lifecycle (automated)
* Turn off or scale down off-peak times
* 40 vs 168 hours/week - 75% savings! 

---

## S3 Storage Class
* How frequently acces (e.g. choose: IA)
* Required retrieval time
* Cost for **100 TB** for 1 month
* Choose proper storage class

| S3 Storage Class | Latency | Min | Cost |
|------------------|---------|-----|------|
| Standard | ms | N/A | $2.304 |
| IA | ms | 30 days | $1.280 |
| Glacier | min-hr | 90 days | $409 |
| Glacier Deep Archive | hours | 180 days | $101 |

---

## Saving Plans
* Similar to **Reserved Instances** discount
  * 1-3 year commitment
  * Full, partial, or no upfront payment
* Compute spend per hour
  * e.g. $50/hr
* Automatically apply to any:
  * Instance family, size tenancy, OS, region
  * Fargate & Lambda
* AWS Cost Explorer

---

## Tools
* AWS Cost Explorer
  * Graph, visualize, analyze spend
  * Saving plans
* AWS Budgets
  * Configure custom budgets & alerts based on budget
* AWS Trusted Advisor  
  * Cost Optimizatin suggestions with service plan

### Cost Anaomaly Detection
* new service - free - you pay only the sub-service (e.g -> SNS)
  * receive a SNS for cost anomaly detection

    
[<img src="https://i.imgur.com/YAHerNR.png">](https://i.imgur.com/YAHerNR.png)

---

## AWS Organizations
* Cost visibility with **single payer account**
* Saving plans & Reserved Instances apply to entire organization
* Volume discounts on combined usage
* Simplify reports
* Limit services with SCPs
* Regular cleanup of sandbox accounts
