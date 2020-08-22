# AWS Organizations

## Acronym
* OU - Organization Unit
* MFA - Multiple-Factor Authentication
* O/P - OutPut

## Doc
* [AWS Organizations Documentations](https://docs.aws.amazon.com/organizations/)
* [What is AWS Organizations?](https://docs.aws.amazon.com/organizations/latest/userguide/orgs_introduction.html?icmpid=docs_orgs_console)

## Intro
* AWS Organizations is an account management service that lets you consolidate
  **multiple AWS accounts into an organization** that you create and centrally manage.
  With AWS Organizations, you can create member accounts and invite existing accounts
  to join your organization. You can organize those accounts and manage them as a group. 

## Power Point
### 01
* OU :

[<img src="https://i.imgur.com/edivSjg.png">](https://i.imgur.com/edivSjg.png)

* Logic :

[<img src="https://i.imgur.com/SZZh26m.png">](https://i.imgur.com/SZZh26m.png)

* AWS Organization (2 organization type) :

[<img src="https://i.imgur.com/LKEV2qD.png">](https://i.imgur.com/LKEV2qD.png)

* Manage cost centrally :

[<img src="https://i.imgur.com/ZHpkRsG.png">](https://i.imgur.com/ZHpkRsG.png)

## AWS Console
1) Create organization : 

[<img src="https://i.imgur.com/mDQUQow.png">](https://i.imgur.com/mDQUQow.png)

2) Two Options :
 * Enable all features
 * Enable only consolidated billing
 
 [<img src="https://i.imgur.com/VW9a6Ah.png">](https://i.imgur.com/VW9a6Ah.png)
 [<img src="https://i.imgur.com/31n6UBr.png">](https://i.imgur.com/31n6UBr.png)
 
 
### Add an account  
#### Invite account
 
 [<img src="https://i.imgur.com/l2uqqBH.png">](https://i.imgur.com/l2uqqBH.png)
 [<img src="https://i.imgur.com/XvpDOOj.png">](https://i.imgur.com/XvpDOOj.png)
 
#### Create account
[<img src="https://i.imgur.com/CKcgGcQ.png">](https://i.imgur.com/CKcgGcQ.png)
[<img src="https://i.imgur.com/ggHqhDL.png">](https://i.imgur.com/ggHqhDL.png)

* Polices\Create policy : 

[<img src="https://i.imgur.com/XODNJel.png">](https://i.imgur.com/XODNJel.png)

* Lambda Only :

[<img src="https://i.imgur.com/UkZW4k3.png">](https://i.imgur.com/UkZW4k3.png)

* Allow\AWS Lambda + Actions: * :

[<img src="https://i.imgur.com/wjY9EGf.png">](https://i.imgur.com/wjY9EGf.png)

* HomePageOrganizations\Policies : 

[<img src="https://i.imgur.com/VGluNmT.png">](https://i.imgur.com/VGluNmT.png)

* Lambda + Attach :

[<img src="https://i.imgur.com/ODifKqY.png">](https://i.imgur.com/ODifKqY.png)

## Demo 01
### First step
1) Create organization :

[<img src="https://i.imgur.com/F1BuPy4.png">](https://i.imgur.com/F1BuPy4.png)

 * Dashboad :
 
[<img src="https://i.imgur.com/5gYZBnc.png">](https://i.imgur.com/5gYZBnc.png)

2) Add account :

[<img src="https://i.imgur.com/VEvfP1m.png">](https://i.imgur.com/VEvfP1m.png)
[<img src="https://i.imgur.com/K8d4BsA.png">](https://i.imgur.com/K8d4BsA.png)

3) Email (invitation) : 

[<img src="https://i.imgur.com/NZ9WNvb.png">](https://i.imgur.com/NZ9WNvb.png)

4) Member Account (MFA) :

[<img src="https://i.imgur.com/0vuEceE.png">](https://i.imgur.com/0vuEceE.png)

5) Inviations (Accept|Decline) : 

[<img src="https://i.imgur.com/P2kvz7l.png">](https://i.imgur.com/P2kvz7l.png)
[<img src="https://i.imgur.com/g5cUkuw.png">](https://i.imgur.com/g5cUkuw.png)
[<img src="https://i.imgur.com/ysCpZR4.png">](https://i.imgur.com/ysCpZR4.png)

6) Masster Account :

[<img src="https://i.imgur.com/dIYvt5d.png">](https://i.imgur.com/dIYvt5d.png)

### Second step
* Tree View : 

[<img src="https://i.imgur.com/gWqMvid.png">](https://i.imgur.com/gWqMvid.png)

1) New OU :

[<img src="https://i.imgur.com/SbRXkim.png">](https://i.imgur.com/SbRXkim.png)
[<img src="https://i.imgur.com/ts57J9Z.png">](https://i.imgur.com/ts57J9Z.png)
[<img src="https://i.imgur.com/7X9ujDh.png">](https://i.imgur.com/7X9ujDh.png)

2) Move Master Account in Production :

[<img src="https://i.imgur.com/UNVXlpI.png">](https://i.imgur.com/UNVXlpI.png)

3) Move CA-Demo in Test : 

[<img src="https://i.imgur.com/HvgCUmH.png">](https://i.imgur.com/HvgCUmH.png)

4) O/P : 

[<img src="https://i.imgur.com/v78ek7F.png">](https://i.imgur.com/v78ek7F.png)
[<img src="https://i.imgur.com/nrGAsP7.png">](https://i.imgur.com/nrGAsP7.png)
