# Directory Services

## Acronym
* AD - Active directory (Microsoft)
* MFA - Multi-factor Authentication

## Doc

## What is Microsoft AD?
* Found on any Windows Server with AD Domain Services
* Database of **objects**: User Accounts, Computer, Printers, File Shares, Security Groups
* Centralized security management, create account, assign permissions
* Objects are organized in **trees**
* A group of trees is a **forest**

### Diagram
[<img src="https://i.imgur.com/quI6sGN.png">](https://i.imgur.com/quI6sGN.png)

---

## AWS Directory Services
1. AWS Managed Microsoft AD
    * Create your own AD in AWS, manage users locally, supports MfA
    * Establish "trust* connections with your on-premise AD
2. AD Connector
    * Directory Gateway (proxy) to redirect to on-premise AD
    * Users are managed on the on-premises AD
3. Simple AD
    * AD-compatible managed directory on AWS 
    * Can't be joined with on-premise AD
    
### Diagram
[<img src="https://i.imgur.com/8vq0qkZ.png">](https://i.imgur.com/8vq0qkZ.png)

---

## Console
* Directory Service
    

[<img src="https://i.imgur.com/TmnEr5w.png">](https://i.imgur.com/TmnEr5w.png)

* Set up directory

[<img src="https://i.imgur.com/h8wnhVr.png">](https://i.imgur.com/h8wnhVr.png)
[<img src="https://i.imgur.com/GcKSxWo.png">](https://i.imgur.com/GcKSxWo.png)
