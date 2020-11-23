# AWS Directory Services

## Doc
* [How to Establish Federated Access to Your AWS Resources by Using Active Directory User Attributes](https://aws.amazon.com/blogs/security/how-to-establish-federated-access-to-your-aws-resources-by-using-active-directory-user-attributes/)

## Acronym
* AD - Active Directory
* RDS - Relational Database Service
* ADFS - AD Federation Service
* SSO - Single Sign-On
* EC2 - Elastic Cloud Compute
* SAML - Security Assertion Markup Language
* DS - Directory Service
* VPC - Virtual Private Cloud

## What is Microsoft AD
* Found on any Windows Server with AD Domain Services
* Databases of **objects**: User Accounts, Computers, Printers, File Shares, Security Groups
* Centralized security management, create account, assign permissions
* Objects are organized in **trees**
* A group of trees is a **forest**

### Diagram
[<img src="https://i.imgur.com/hFcTDIT.png">](https://i.imgur.com/hFcTDIT.png)

---

## What is ADFS ?
* ADFS: provide SSO across applications
* SAML across 3<sup>rd</sup> party: AWS Console, Dropbox, Office365, etc...

### Diagram
[<img src="https://i.imgur.com/s068ShD.png">](https://i.imgur.com/s068ShD.png)

---

## AWS Directory Services
1) AWS Managed Microsoft AD (cloud)
  * Create your own AD in AWS, manage users locally, supports MFA
  * Establish "trus" connections with your on-premise AD
2) Ad Connector
  * Directory Gateway (proxy) to redirect to on-premise AD
  * Users are managed on the on-premise AD
3) Simple AD
  * AD-compatible managed directory on AWS 
  * cheaper

### Diagram
[<img src="https://i.imgur.com/QTywaaq.png">](https://i.imgur.com/QTywaaq.png)

---

## AWS DS - AWS Managed Microsoft AD
* Managed Service: Microsoft AD in your AWS VPC
* EC2 Windows Instances:
  * EC2 Windows instances can join the domain & run traditional AD applications (SharePoint, etc)
  * Seamlessly Domain Join Amazon EC2 Instances from Multiple Accounts & VPCs
* Integrations:
  * RDS for SQL Server, AWS Workspaces, Quicksight...
  * AWS SSO to provide access to 3<sup>rd</sup> party applications

### Diagram
