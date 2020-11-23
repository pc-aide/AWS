# Identity Federation & Cognito

## Doc
* [ID roles providers SAML](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_providers_saml.html)
* [Enable SAML federated users to access the AWS Console](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_providers_enable-console-saml.html)
* [AWS Federated Authentication with ADFS](https://aws.amazon.com/blogs/security/aws-federated-authentication-with-active-directory-federation-services-ad-fs/)
* [AWS Security Blog Enabling Federation to AWS Using Windows Active Directory, ADFS, and SAML 2.0](https://aws.amazon.com/blogs/security/enabling-federation-to-aws-using-windows-active-directory-adfs-and-saml-2-0/)
* [Providing access to externally authenticated users (identity federation) ](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_common-scenarios_federated-users.html)
* [Using Web Identity Federation](https://docs.amazonaws.cn/en_us/amazondynamodb/latest/developerguide/WIF.html)
* [Using Cognito for mobile apps](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_providers_oidc_cognito.html)

## Acronym
* SAML - Security Assertion Markup Language
* SSO - Single Sign On
* IAM - Identity & Access Management
* Active Directory
* IdP - Identity Provider
* MFA - Multi-Factor Authentication
* WIF - Web Identity Federation
* OIDC - OpenID Connect

## Identity Federation in AWS
* Federation lets users outside of AWS to assume temporary role for accessing AWS resources
* These users assume identity provided access role
* Federations can have my flavors:
  * SAML 2.0
  * Custom Identity Broker
  * Web Identity Federation with Cognito (Cognito User Identity !?)
  * Web Identity Federation without Cogntio
  * SSO
  * Non-SAML with AWS Microsoft AD
* **Using federation, you dont't need to create IAM users (user managment is outside of AWS**)

### Diagram
[<img src="https://i.imgur.com/XWXHZbS.png">](https://i.imgur.com/XWXHZbS.png)

---

## SAML 2.0 Federation
* To integrate Active Directory / ADFS with AWS (or any SAML 2.0)
* Provides access to AWS Console or CLI (through temporary creds)
* No need to create an IAM user for each of your employees

### Diagram
[<img src="https://i.imgur.com/mk0rEJP.png">](https://i.imgur.com/mk0rEJP.png)

* AWS Console

[<img src="https://i.imgur.com/uXzCRzd.png">](https://i.imgur.com/uXzCRzd.png)

---

## SAML 2.0 Federation - ADFS
* Same process as with any SAML 2.0 compatible IdP

[<img src="https://d1.awsstatic.com/security-center/SecurityBlog/federated_auth_with_adfs_25.dc86ecbfbbf80af3f553e7374d2a55ad1afb7016.png">](https://d1.awsstatic.com/security-center/SecurityBlog/federated_auth_with_adfs_25.dc86ecbfbbf80af3f553e7374d2a55ad1afb7016.png)

---

## SAML 2.0 Federation
* Needs to setup a trust between AWS IAM & SAML (both ways)
* SAML 2.0 enables web-based, cross domain SSO
* Uses the STS API: AssumeRoleWithSAML
* Note federation through SAML is the "old way" of doing things
* SSO Federation is the new managed & smpler way
* MFA - Multi-Factor Authentication
* TVM - Token Vending Machine
* WIF - Web Identity Federation

---

## Custom Idenity Broker Application
* Use only if idenity provider is not compatible with SAML 2.0
* **The identity borker must determine the appropriate IAM policy**
* Uses the STS API:**AssumeRole** or **GetFederationToken**

### Diagram
[<img src="https://i.imgur.com/YVOypej.png">](https://i.imgur.com/YVOypej.png)

---

## Web Identity Federation - AssumeRoleWithWebIdentity
* Not recommended by AWS - use Cognito instead (allows for anonymous users, data 
  synchronization, MFA)
  
### Diagram
[<img src="https://i.imgur.com/MKWToiC.png">](https://i.imgur.com/MKWToiC.png)

---

## WIF - AWS Cognito
* Preferred way for WIF
  * Create IAM Roles using Cognito with the last privilege needed
  * Build trust between the OIDC IdP & AWS
* Congito benefits:
  * Support for anonymous users
  * Support for MFA
  * Data synchronization
* Cognito replaces a TVM
  
### Diagram
[<img src="https://i.imgur.com/0fU0IEI.png">](https://i.imgur.com/0fU0IEI.png)

---

## WIF - IAM Policy
* After being authenticated with WIF, you can identify the user with an IAM policy variable
* **Examples:**
  * Cognito-identity.amazonaws.com:sub
  * www.amazon.com:user_id
  * graph.facebook.com:id
  * accounts.google.com:sub
````json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": ["s3:ListBucket"],
      "Resource": ["arn:aws:s3::myBucket"],
      "Condition": {"StringLike": {"s3:prefix": ["Amazon/mynumbersGame/${www.amazon.com:user_ide}/*"]}}
    },
    {
      "Effect": "Allow",
      "Action": [
        "s3:GetObject",
        "s3:PutObject",
        "s3:DeleteObject"
      ],
      "Resource": [
        "arn:aws:s3::myBucket/amazon/mynumbersGame/${www.amazon.com:user_id}",
        "arn:aws:s3::myBucket/amazon/mynumbersGame/${www.amazon.com:user_id}/*"
      ]
    }
  ]
}
````
