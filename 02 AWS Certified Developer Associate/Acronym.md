# Acronym

## Table
## Acronym
| N | Acronym | Definition            | E.g                                           |
| - | ------- | --------------------- | ----------------------------------------------|
| 1 | EC2     | Elastic Compute Cloud | Windows, Linux (instances of Virtual Machines)|
| 2 | EBS     | Elastic Block store   | |
| 3 | ELB     | Elastic Load Balancing| |
| 4 | SG     | Security Group    | |
| 5 | AMI     | Amazon Machine Image  | Windows2019, Ubutnu18.04, CentOS7, WordPress, vSRX, F5-Big, etc |
| 6 | IAM     | Identity & Access Management| Users, groups, Roles, Policies |
| 7 | BYOL    | Bring Your Own License | 
| 8 | ENI     | Elastic Network Interfaces | VPC endpoint |
| 9 | SSL     | Secure Sockets Layers |
| 10 | TLS | Transport Layer Security | 
| 11 | ACM | AWS Certificate Manager | ex: ACM for ALB (HTTPS) |
| 12 | SNI | Server Name Indication |
| 13 | ALPN | Application-Layer Protocol Negotiation | ALPN Policy |
| 14 | ASG | Auto Scaling Group |
| 15 | GP2 SSD | General purpose SSD| Create new EBS volume |
| 16 | EFS | Elastic File System | e.g: SMB, CIFS, etc |
| 17 | NFS | Network File System | e.g: CIFS |
| 18 | AZ  | Availability Zone | ca-central-1a, us-west-1d, etc |
| 19 | KMS | Key Management Service | 
| 20 | API | Application Program Interface | 
| 21 | DS  | Disaster Recovery |
| 22 | RDS | Relational database service | RDS {MySQL, Oracle, Aurora, PostgreSQL, Microsoft SQL Server, MariaDB} |
| 23 | TTL | Time-to-live | ping -t 5 rds.ca (default ttl: 60 Linux) - so ttl=1 so you'll never exit your ISP before to reach the target |
| 24 | TDE | Transparent Data Encryption | |
| 25 | NACL | Nework Access Control List | |
| 26 | NAT | Network Address Translation | e.x. 192.168.1.10:80 (client to ask to srv) -> 192.168.1.1:6037 (router to talked ISP) -> 11.22.33.44:6037 (ISP) who talked to srv to get answer | 
| 27 | DX | Direct Connect | |
| 28 | IGW | Internet Gateway | at the VPC level, provide Internet Access |
| 29 | SSE | Server Side Encryption | SSE-S3, SSE-KMS, SSE-C |
| 30 | ACL | Access Control List | {Object, Bucket} ACL |
| 31 | ARN | Amazon Resource Name | e.g: arn:aws:s3:::s3-ca-website |
| 32 | CORS | Cross-Origin Resource Sharing | |
| 33 | ECS | Elastic Container Service | |
| 34 | WORM | Write Once Read Many | a WORM model |
| 35 | CDN | Content Delivery Network | CloudFront |
| 36 | OAI | Origin Access Identity | |
| 37 | ECR | Elastic Container Registry | |
| 38 | EKS | Elastic Kubernetes Service | |
| 39 | EB  | Elastic Beanstalk | |
| 40 | SQS | Simple Queue Service | |
| 41 | CI/CD | Continuous Integration, Continuous Delivery | |
| 42 | SNS | Simple Notification Service | |
| 43 | SSM | Simple Systems Manager | SSM Agent | Software can installed on EC2 or on-premise |
| 44 | CF  | CloudFormation | | 
| 45 | CW  | CloudWatch | | 
| 46 | SLA | Service-Level Agreement | |
| 47 | CMK | Customer Master key | ex: SQS\Encryption: CMK alias |
| 48 | DLQ | Dead Letter Queue | |
| 49 | FIFO | First In First Out (ordering of messages in the queue) | | 
| 50 | Pub/Sub | Publish subscribe | SNS |
| 51 | KCL | Kinesis Client Library | |
| 52 | ETL | Extract, Transform, Load | Big data |
| 53 | FaaS | Function as a Service | ex.: Lambda |
| 54 | SAM | Serverless Application Model | ex: SAM framework |
| 55 | RDBMS | Relational Database Management System | ex: Oracle, MySQL, PostgreSQL, etc | 
| 56 | RCU & WCU | Read Capacity Units & Write Capacity Units | DynamoDB |
| 57 | LSI | Local Secondary Index | DynamoDB - LSI | 
| 58 | GSI | Global Secondary Index | DynamoDB - GSI |
| 59 | DAX | DynamoDB Accelerator | |
| 60 | EMR | Elastic MapReduce | AWS EMR (Managed Hadoop Framework) | 
| 61 | DMS | Database Migration Service | Amazon DMS | 
| 62 | CRUD | Create/Read/Update/Delete | CRUD operations (DynamoDB) | 
| 63 | WAF | Web Application Firewall | ex: API Gateway\<stage>\WAF |
| 64 | VTL | Velocity Template Language | API Gateway - use VTL: for loop, if etc |
| 65 | REST | REpresentative State Transfer | |
| 66 | CUP | Cognito User Pools | |
| 67 | JWT | JSON Web Token | CUP |
| 68 | STS | Security Token Service | Get temp creds (STS) |
| 69 | CIP | Cognito Identity Pools | |
| 70 | MITM | Man In The Middle attack | |
| 71 | DEK | Data Encryption Key (Envelope Encryption) | DEK (big file: ex: 10 MB) |
| 72 | SSE-C | SSE-Customer | own encryption keys (S3) |
| 73 | SES | Simple Email Service | |
| 74 | OLTP | OnLine Transaction Processing | RDS |
| 75 | OLAP | OnLine Analytic Processing | Redshift |
| 76 | SAML | Security Assertion Markup Language | |
| 77 | FPGAs | Field-Programmable Gate Arrays | ex-instance: FPGA Developer AMI|
| 78 | IMDS | Instance MetaData Service | curl 169.254.169.254/latest/meta-data/ |
| 79 | BLOB | Binary Large OBject data | |
| 80 | DAS | Direct-Attached Storeage | used for block storage |
| 81 | SAN | Storage Area Network | used for block storage |
| 82 | CID | Confidentiality, Integrity, Availability | CID Model | 
| 83 | IOPS | Input/Output operation Per Second capacity | |
| 84 | BI | Business Intelligence | Redshift | 
| 85 | LIFO | Last-In-First-Out | |
| 86 | RRS | Reduced Redundancy Storage | S3 class RRS |
| 87 | SWF | Simple WorkFlow Service | Amazon SWF |
| 88 | IaC | Infrastructure as Code | |
| 89 | SCP | Service Control Policies | SCP (IAM) | 
| 90 | ORM | Object Relational Mapping | Convert between db records & in-code "objects" |
