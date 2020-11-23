# STS

## Acronym
* STS - Security Token Service
* IAM - Identity & Access Management
* SAML - Security Assertion Markup Language
* IdP - identity provider
* MFA - Multi-Factor Authentication

## Using STS to Assume a Role
* Define a n IAM Role within your account or cross-account
* Define which principals can access this IAM Role
* Use AWS STS to retrieve credentials & impersonate the IAM Role you have access to (**AssumeRole API**)
* Temporary credentials can be valid between 15 minutes to 1 hour

### Diamgram
[<img src="https://i.imgur.com/B88C7SI.png">](https://i.imgur.com/B88C7SI.png)

---

## Use case
* Provide access for an IAM user in one AWS account that you own to access resources in another account that your own
* Provide access to IAM users in AWS accounts owned by third parties
* Provide access for services offered by AWS to AWS resources
* Provide access for externally authenticated user (identity federation)
* Ability to revoke active sessions & credentials for a role (by adding a policy using a time statement - AWSRevokeOlderSessions)
* When you assume a role (user, application or service), you give up your original
  permissions & take the permissions assigned to the role
  
---

## Providing Access to an IAM User in Your or Another AWS Account that you own
* You can gran your IAM users permissions to switch to roles within your AWS account
  or to roles defined in other AWS accounts **that you own**
* <ins>Benifits</ins>: 
   * You must explicitly grant your users permission to assume the role
   * Your users must actively switch to the role using the AWS Management Console or assume
    the role using the AWS CLI or AWS API
   * **You can add MFA protection to the role** so that only users who sign in with an MFA
    device can assume the role
   * Least privilege + auditing using CloudTrail
  
### Diagram
[<img src="https://i.imgur.com/PhPzF49.png">](https://i.imgur.com/PhPzF49.png)

---

## Cross account access with STS
[<img src="https://i.imgur.com/FKNoSem.png">](https://i.imgur.com/FKNoSem.png)

---

## Providing Access to AWS Accounts Owned by Third Parties
* Zone of trust = accounts, organizations that you own 
* Outside Zone of Trust = 3<sup>rd</sup> parties
* Use IAM Access Analyzer to find out which resources are exposed
* For granting access to a 3<sup>rd party:
  
  
---

## The confused deputy
[<img src="https://i.imgur.com/k1BI4am.png">](https://i.imgur.com/k1BI4am.png)

---

## STS Important APIs
* **AsumeRole**: access a role within your account or cross-account
* **AssumeRoleWithSAML**: return credentials for user logged with SAML
* **ASSumeRoleWithWebIdentity**: return creds users logged with an IdP
  * Ex.: providers include Cognito, Login with Amazon, Facebook, Google, or any OpenID
    Connect-compatible identity provider
  * **AWS recommends using Cognito instead**
* **GetSessionToken**: for MFA, from a user or AWS account root user
* **GetFederationToken**: obtain temporary creds for a federated user, usually a proxy app
  that will give the creds to a distributed app inside a corporate network
