# Secrets Manager

## Acronym
* RDS - Relational Database Service
* KMS - Key Management Service

## Intro
* Newer service, meant for storing secrets
* Capability to force **rotation of secrets** every X days
* Automate generation of secrets on rotation (uses Lambda)
* Integration with **RDS** (MySQL, PostgreSQL, Aurora)
* Secrets are encrypted using KMS
* Mostly meant for RDS integration
