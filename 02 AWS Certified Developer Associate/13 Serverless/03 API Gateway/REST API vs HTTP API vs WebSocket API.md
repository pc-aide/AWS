# REST API vs HTTP API vs WebSocket API

## Acronym
* REST - REpresentative State Transfer
* CORS - Cross Origin Resource Sharing

## Doc
* [Choosing between HTTP APIs and REST APIs](https://docs.aws.amazon.com/apigateway/latest/developerguide/http-api-vs-rest.html)

## HTTP API vs REST API
* HTTP APIs
    * Low-latency, cost-effective AWS Lambda proxy, HTTP proxy APIs & private integration (no data mapping)
    * support OIDC & OAuth 2.0 authorization, & built-in support for CORS
    * No usage plans & API keys
* REST APIs 
    * All features (exept native OpenID Connect/OAuth 2.0)
    
* Table:

| Authorizers                          | HTTP API | REST API |
| ------------------------------------ | -------- | -------- |
| AWS Lambda                           |          | ✔        |
| IAM                                  |          | ✔        |
| Amazon Cognito                       | ✔\*      | ✔        |
| Native OpenID connect<br>/ OAuth 2.0 | ✔        |

---

## WebSocket API - Overview
* What's WebSocket?
    * Two-way interactive communication between a user's browser & a server
    * Server can push information to the client
    * This enables **statefull** application use cases
* WebSocket APIs are often used in **real-time applications** such as **chat** applications, collaboration platforms,
  multiplayer games, & **financial trading platforms (ex: stock actions)**
* Works with AWS Services (Lambda, DynamoDB) or HTTP endpoints
  
* WebSocket:

[<img src="https://i.imgur.com/wt9PVKf.png">](https://i.imgur.com/wt9PVKf.png)

---

## Console
* API Gateway\create API
    * API type:
    
[<img src="https://i.imgur.com/IbISCKo.png">](https://i.imgur.com/IbISCKo.png)
