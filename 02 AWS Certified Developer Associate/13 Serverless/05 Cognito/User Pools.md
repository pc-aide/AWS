# User Pools

## Doc

## Acronym
* CUP - Cognito User Pools
* MFA - Multi-Factor Authentication
* JWT - JSON Web Token
* ALB - Application Load Balancer
* ECS - Elastic Container Service

## CUP - User Features
* Create a serverless db of user for your web & mobiles apps
* Simple login: Username (or email) / password combination
* Password reset
* Email & Phone Number Verification
* MFA
* Federated Identities: users from Facebook, Google, SAML...
* Feature: blok users if their credentials are compromised elsewhere
* Login sends back a JSON Web Token (JWT)

### Diagram
[<img src="https://i.imgur.com/7E0bKe0.png">](https://i.imgur.com/7E0bKe0.png)

---

## Integration
* CUP integrates with **API Gateway** & **ALB**

### Diagram
[<img src="https://i.imgur.com/sfqJda8.png">](https://i.imgur.com/sfqJda8.png)
