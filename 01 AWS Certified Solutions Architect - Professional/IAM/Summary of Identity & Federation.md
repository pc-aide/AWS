# Summary of Identity & Federation

## Acronym
* SAML - Security Assertion Markup Language
* RDS - Relational Database Service
* MFA - Multi-Factor Authentication
* IdP - Identity Provider
* SSO - Single Sign-On

## Intro
* Users & Accounts all in AWS
* AWS Organizations
* Federation with SAML
* Federation without SAML with a custom IdP (GetFederationToken)
* Federation with SSO for multiple accounts with AWS Organizations
* Web Identity Federation (not recommended)
* Cognito for most web & mobile application (has anonymous mode, MFA)
* Active Directory on AWS:
  1) Microsoft AD: standalone or setup trust AD with on-premise, has MFA, seamless join, RDS integration
  2) AD Connector: proxy requests to on-premise
  3) Simple AD: standalone & cheap AD-compatbile with no MFA, no advanced capabilities
* Single Sing-On to connect to multiple AWS Accounts (Organization) & SAML apps
