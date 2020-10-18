# User Pools vs Identity Pools

## Acronym
* DB - Database
* IAM - Identity & Access Management
* CUP - Cognito User Pools
* CIP - Cognito Identity Pools
* STS - Security Token Service

## Doc

## Intro
* Cognito User Pools:
    * DB of users for your web & mobile application
    * Allows to federate login through Public Social, OIDC, SAML...
    * Can customize the hosted UI for authentication (inluding the logo)
    * Has triggers with Lambda during the authentication flow
* Cognito Identity Pools:
    * Obtain AWS credentials for your users
    * Users can logi nthrough Public Social, OIDC, SAML & Cognito User Pools
    * Users can be unauthenticated (guests)
    * Users are mapped to IAM roles & policies, can leverage policy variables
* CUP + CIP = manage user/password + access AWS services
    * CUP = manage user/password
    * CIP = access AWS services
    
### Diagram with CUP
[<img src="https://i.imgur.com/NsEDZaI.png">](https://i.imgur.com/NsEDZaI.png)
