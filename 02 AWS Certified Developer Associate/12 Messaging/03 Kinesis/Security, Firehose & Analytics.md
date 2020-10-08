# Security, Firehose & Analytics

## Doc

## Acronym
* IAM - Identity & Access Management
* KMS - Key Management Service
* VPC - Virtual Private Cloud

## Security
* Control access/authorization using IAM policies
* Encryption in flight using HTTPS endpoints
* Encryption at rest using KMS
* Possibility to encrypt/decrypt data client side (harder)
* VPC Endpoints available for Kinesis to access within VPC

---

## Data Analystics
* Perform real-time analytics on Kinesis Streams using SQL
* Kinesis Data Analytics:
    * Auto Scaling
    * Managed: no servers to provision
    * Continuous: real time
* Pay for actual consumption rate
* Can create streams out of the real-time queries

---

## Firehose
* Fully Managed Service, no administration
* Near Real Time (60 seconds latency)
* Load data into Redshift/S3/ElasticSeach/Splunk
* Automatic scaling
* Support many data fromat (pay for conversion)
* Pay for the amount of data going through Firehose
