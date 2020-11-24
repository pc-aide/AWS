# Single Sing-On (SSO)

## Acronym
* AD - Active Directory

## Doc
* [Introducing AWS Single Sign-On](https://aws.amazon.com/blogs/security/introducing-aws-single-sign-on/)

## Acronym
* SSO - Single Sing-On
* SAML - Security Assertion Markup Language
* IdP - Identity Provider

## Intro
* Centrally manage Single Sign-On to access **multiple accounts** & **3<sup>rd</sup> party business applications**
* Integrated with **Organizations**
* Support **SAML 2.0** markup
* Integration with on-premise **Active Directory**
* Centralized permissions management
* Centralized auditing with CloudTrail

### Img
[<img src="https://i.imgur.com/TEDtCYC.png">](https://i.imgur.com/TEDtCYC.png)


---

## SSO - Setup with AD
* <ins>Options for integration:</ins>
  1) Standalone AWS Managed Microsoft AD
  2) AD Connector to on-premise AD
  3) AWS Managed Microsoft AD with two-way forest trust with on-premise AD
  
### Diagram
[<img src="https://i.imgur.com/9y77Bc7.png">](https://i.imgur.com/9y77Bc7.png)

--

## SSO - vs AssumeRoleWithSAML
[<img src="https://i.imgur.com/3rHr0q3.png">](https://i.imgur.com/3rHr0q3.png)
