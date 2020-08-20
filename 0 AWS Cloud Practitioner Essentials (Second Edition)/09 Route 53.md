# Route 53

## Terminology
* Amazon Route 53 registrar
  * Alternative godaddy

## Acronym
* DNS - Domain Name System
* NS - Name Server
* FQDN - Full Qualified Domain Name
* SOA record - Start of Authority record
    * record is implicit

## Ports
* DNS : 53

## What is Route 53?
[<img src="https://i.imgur.com/ogkv9c0.png">](https://i.imgur.com/ogkv9c0.png)

## How does it work?
### User
* type example.com in his chrome
[<img src="https://i.imgur.com/8dhax9f.png">](https://i.imgur.com/8dhax9f.png)

### Translation 
* example.com -> IPv Public -> 54.85.178.219
[<img src="https://i.imgur.com/AfNEGXn.png">](https://i.imgur.com/AfNEGXn.png)

## Creating a Hosted Zone
* First step: creating a Hosted Zone
* This is where your DNS data be kept

[<img src="https://i.imgur.com/778ccCT.png">](https://i.imgur.com/778ccCT.png)
[<img src="https://i.imgur.com/vsnccXO.png">](https://i.imgur.com/vsnccXO.png)
[<img src="https://i.imgur.com/wfz1FRL.png">](https://i.imgur.com/wfz1FRL.png)

## E.g
### AWS Console
1) Instance

[<img src="https://i.imgur.com/gNElgo2.png">](https://i.imgur.com/gNElgo2.png)

2) Ipv4 Public (httpd)

[<img src="https://i.imgur.com/hlD6nS1.png>](https://i.imgur.com/hlD6nS1.png)
