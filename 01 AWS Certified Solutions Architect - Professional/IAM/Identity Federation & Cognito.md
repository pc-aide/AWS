# Identity Federation & Cognito

## Doc
* [ID roles providers SAML](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_providers_saml.html)
* [Enable SAML federated users to access the AWS Console](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_providers_enable-console-saml.html)

## Acronym
* SAML - Security Assertion Markup Language
* SSO - Single Sign On

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
