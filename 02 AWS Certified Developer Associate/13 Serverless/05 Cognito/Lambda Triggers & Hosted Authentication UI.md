# Lambda Triggers & Hosted Authentication UI

## Acronym
* CUP - Cognito User Pools

## Doc
* [Customizing User Pool Workflows with Lambda Triggers](https://docs.aws.amazon.com/cognito/latest/developerguide/cognito-user-identity-pools-working-with-aws-lambda-triggers.html)
* [Launch – Amazon Cognito User Pools General Availability: App Integration and Federation](https://aws.amazon.com/blogs/aws/launch-amazon-cognito-user-pools-general-availability-app-integration-and-federation/)

## Intro
* CUP can invoke a Lambda function synchronously on these triggers:

| User Pool Flow             | Operation                           | Description                                                   |
|----------------------------|-------------------------------------|---------------------------------------------------------------|
| Custom Authentication Flow | Define Auth Challenge               | Determines the next challenge in a custom auth flow           |
|                            | Create Auth Challenge               | Creates a challenge in a custom auth flow                     |
|                            | Verify Auth Challenge Response      | Determines if a response is correct in a custom auth flow     |
| Authentication Events      | Pre Authentication Lambda Trigger   | Custom validation to accept or deny the sign-in request       |
|                            | Post Authentication Lambda Trigger  | Event logging for custom analytics                            |
|                            | Pre Token Generation Lambda Trigger | Augment or suppress token claims                              |
| Sign-Up                    | Pre Sign-up Lambda Trigger          | Custom validation to accept or deny the sign-up request       |
|                            | Post Confirmation Lambda Trigger    | Custom welcome messages or event logging for custom analytics |
|                            | Migrate User Lambda Trigger         | Migrate a user from an existing user directory to user pools  |
| Messages                   | Custom Message Lambda Trigger       | Advanced customization and localization of messages           |
| Token Creation             | Pre Token Generation Lambda Trigger | Add or remove attributes in Id tokens                         |


---

## Hosted Authentication UI
* Cognito has a **hosted authentication UI** that you can add to your app to handle sign-up & sing-in workflows
* Using the hosted UI, you have a foundation for integration with socail logins, OIDC or SAML
* Can customize with a **custom logo** & **custom CSS**

[<img src="https://i.imgur.com/eiPMPXZ.png">](https://i.imgur.com/eiPMPXZ.png)
[<img src="https://i.imgur.com/gDap6fo.png">](https://i.imgur.com/gDap6fo.png)
