# SSM Parameter Store vs Secrets Manager

## Doc

## Acronym
* SSM - Simple System Manager
* RDS - Relational Database Service
* KMS - Key Management Service

## Intro
* Secrets Manager (**$$$**):
    * Automatic rotation of secrets with Lambda
    * Integration with RDS, Redshift, DocumentDB
    * KMS encryption is mandatory
    * Can integration with CloudFormation
* SSM Parameter Store (**$**):
    * Simple API
    * No secret rotation
    * KMS encryption is optional
    * Can integration with CloudForamtion
    * Can pull a Secrets Manager secret using the SSM Parameter Store API
