# SAM

## Acronym
* SAM - Serverless Application Model
* CI/CD - Continuous Integration/Continuous Delivery

## Intro
* Framework for developing & deploying serverless applications
* All the configuration is YAML code
  * Lambda Function (AWS::Serverless::Function)
  * DynamoDB tables (AWS::Serverless::SimpleTable)
  * API Gateway (AWS::Serverless::API)
  * Cognito User Pools
* SAM can help you to run Lambda, API Gateway, DynamoDB locally
* SAM can use CodeDeploy to deploy Lambda functions (traffic shifting)
* **Leverages CloudFormation in the backend**

---

## CI/CD Architecture for SAM
[<img src="https://i.imgur.com/HStfOcf.png">](https://i.imgur.com/HStfOcf.png)
