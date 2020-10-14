# Security & Other

## Acronym
* IAM - Identity & Access Management
* KMS - Key Managment Service
* SSL - Secure Sockets Layers
* TLS - Tansport Layer Security
* RDS - Relational Database Service
* DMS - Database Migration Service

## Doc

## Security & Other Features
* Security:
    * **VPC Endpoints** available to access DynamoDB without internet
    * Access fully controlled by IAM
    * Encryption at rest using KMS
    * Encryption in transit using SSL/TLS
* Backkup  & Restore feature avaiable
    * Point in time restore like RDS
    * No performance impact
* Global Tables
    * Multi region, fully replicated, high performance
* Amazon DMS can be used to migrate to DynamoDB (from Mongo, Oracle, MysQL, S3, etc...)
* You can launch a local DynamoDB on your computer for development purposes
