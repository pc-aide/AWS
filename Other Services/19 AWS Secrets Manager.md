# 19 AWS Secrets Manager

## Acronym
* API - Application Process Interface
* DB - Database
* cred - credential

## Doc
* [AWS Secrets Manager Documentation](https://docs.aws.amazon.com/secretsmanager/)

## Intro
* AWS Secrets Manager helps you to securely encrypt, store, and retrieve credentials
  for your databases and other services. Instead of hardcoding credentials in your
  apps, you can make calls to Secrets Manager to retrieve your credentials whenever
  needed. Secrets Manager helps you protect access to your IT resources and data by
  enabling you to rotate and manage access to your secrets. 
  
## Power Point
### 01
* Code has to call an API using an API key
* How do we generally code it
* import creds (bad idea) 

[<img src="https://i.imgur.com/PD4AUOG.png">](https://i.imgur.com/PD4AUOG.png)

* Lambda + AWS Secrets Managers

[<img src="https://i.imgur.com/tv71QJt.png">](https://i.imgur.com/tv71QJt.png)

### 02
#### What do customers want to do?
[<img src="https://i.imgur.com/wMV9WEP.png">](https://i.imgur.com/wMV9WEP.png)

#### What callenges are they facing?
[<img src="https://i.imgur.com/pHBh3H2.png">](https://i.imgur.com/pHBh3H2.png)

#### Lifecycle management for secrets such as DB creds & API keys
[<img src="https://i.imgur.com/MLTPtcy.png">](https://i.imgur.com/MLTPtcy.png)

#### Key features
[<img src="https://i.imgur.com/a7OhgED.png">](https://i.imgur.com/a7OhgED.png)
[<img src="https://i.imgur.com/cJkf96H.png">](https://i.imgur.com/cJkf96H.png)

## Demo 01
### Store & retrive SSH key
[<img src="https://i.imgur.com/d5UdQDD.png">](https://i.imgur.com/d5UdQDD.png)

1) AWS Console\Service\Secret Manager :

[<img src="https://i.imgur.com/QJeLsW9.png">](https://i.imgur.com/QJeLsW9.png)
[<img src="https://i.imgur.com/vTJJpSB.png">](https://i.imgur.com/vTJJpSB.png)

2) Store a new secret :

