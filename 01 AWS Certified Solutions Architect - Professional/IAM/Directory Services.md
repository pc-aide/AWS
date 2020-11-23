# Directory Services

## Doc
* [How to Establish Federated Access to Your AWS Resources by Using Active Directory User Attributes](https://aws.amazon.com/blogs/security/how-to-establish-federated-access-to-your-aws-resources-by-using-active-directory-user-attributes/)
* [How to Connect Your On-Premises Active Directory to AWS Using AD Connector](https://aws.amazon.com/blogs/security/how-to-connect-your-on-premises-active-directory-to-aws-using-ad-connector/)

## Acronym
* AD - Active Directory
* RDS - Relational Database Service
* DC - Domain Controller
* MFA - Multi-Factor Authentication
* AZ - Availability Zone
* ADFS - AD Federation Service
* SSO - Single Sign-On
* DX - Direct Connect
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
* Standalone repository in AWS or joined to on-premise AD
* Multi AZ deployment of AD in 2 AZ, # of DC can be increased for scaling
* automated backups

### Diagram
[<img src="https://i.imgur.com/dTPXW73.png">](https://i.imgur.com/dTPXW73.png)

---

## AWS Microsoft Managed AD - Integrations
[<img src="https://i.imgur.com/dMbxdMl.png">](https://i.imgur.com/dMbxdMl.png)

---

## Connect to on-premises AD
* Ability to connect your on-premise AD to AWS Managed Microsoft AD
* Must establish a Direct Connect (DX) or VPN connection
* Can setup 3 kinds of forest trust:
 1) **One-way trust**:
  * AWS => On-Premise
 2) **One-way trust**:
  * On-Premise => AWS
 3) **Two-way forest trust**:
 * AWS <=> On-Premise
* Forest trust is different than synchronization (**replication is not supported**)

### Diagram
[<img src="https://i.imgur.com/SvXyArQ.png">](https://i.imgur.com/SvXyArQ.png)

---

## Solution Architecture: AD Replication
* You may want to create a replica of your AD on EC2 in the cloud to minimize latency 
  of case DX or VPN goes down
* Establish trust between the AWS Managed Microsoft AD & EC2

### Diagram
[<img src="https://i.imgur.com/1aJzNAq.png">](https://i.imgur.com/1aJzNAq.png)

---

## Direcotry Services AD Connector
* **AD Connector** is a directory **gateway** to redirect directory requests to your
  on-premises Microsoft AD
* No caching capability
* Manage users solely on-premise, no possibility of setting up a trust
* VPN or Direct Connect
* Doesn't work with SQL Server, doesn't do seamless joining, can't share directory

### Diagram
[<img src="https://i.imgur.com/2uMgwNM.png">](https://i.imgur.com/2uMgwNM.png)

---

## Directory Services Simple AD
* **Simple AD** is an inexpensive AD - compatible service with the common directory features
* Supports joining EC2 instances, manage users & groups
* Does not support MFA, RDS SQL server, AWS SSO
* Small: 500 users, large: 5k users
* Powered by Sambda 4, compatible with Microsoft AD
* Lower cost, low scale, basic AD compatible, or LDAP compatibility
* No trust relationship
