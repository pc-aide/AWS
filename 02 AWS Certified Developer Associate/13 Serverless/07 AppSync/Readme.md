# AppSync

## Acronym
* IAM - Identity & Access Management

## Doc

## Intro
* **AppSync** is a managed service that uses **GraphQL**
**GraphQL** makes it easy for applications to get exactly the data they need
* This includes combining data from **one or more sources**
    * NosQL data stores, Relational databases, HTTP APIs...
    * Integrates with DynamoDB, Aurora, ElasticSearch & others
    * Custom sources with Lambda
* Retrieve data in **real-time with WebSocket or MQTT on WebSocket**
* For mobile apps: local data access & data synchronization
* It all starts with uploading one **GraphQL schema**

---

## GraphQL example
[<img src="https://i.imgur.com/AirAow7.png">](https://i.imgur.com/AirAow7.png)

### Diagram
[<img src="https://i.imgur.com/HuFQTxN.png">](https://i.imgur.com/HuFQTxN.png)

---

## Security
* There are four ways can authorize applications to interact with your AppSync GraphQL API:
    1. API_KEY
    2. AWS_IAM: IAM users/roles/cross-account access
    3. OPENID_Connect: OpenID Connect provider/JSON Web Token
    4. AMAZON_COGNITO_USER_POOLS
* For custom domain & HTTPS, use CloudFront in front of AppSync
