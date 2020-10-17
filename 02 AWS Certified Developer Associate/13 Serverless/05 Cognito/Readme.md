# Cognito

## Acronym
* ALB - Application Load Balancer
* IAM - Identity & Access Management

## Doc

## Intro
* We want to give our users an identity so that they can interact with our application
1. **Cognito User Pools**:
    * Sign in functionality for app users
    * Integrate with API Gateway & ALB
2. **Cognito Idenity Pools (Federated Identity)**:
    * Provide AWS credentials to users to they can access AWS resources directly
    * Integrate with Cognito User Pools as an identity provider
3. **Cognito Sync**:
    * Synchronize data from device to Cognito
    * Is deprecated & replaced by AppSync
* **Cognito vs IAM**: "hundreds of users", "mobile users", "authenticate with SAML"
