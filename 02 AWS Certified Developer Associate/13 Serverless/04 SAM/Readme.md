# SAM

## Acronym
* SAM - Serverless Application Model

## Doc

## Intro
* Framework for developing & deploying serverless applications
* All the configuration is YAML code
* Generate complex CloudFormation from simple SAM YAML file
* Supports anything from CloudFormation: Outputs, Mappings, Parameters, Resources...
* Only two cammands to deploy to AWS 
* SAM can use CodeDeploy to deploy Lambda functions
* SAM can help you to run Lambda, API Gateway, DynamoDB locally

---

## Recipe
* **Transform Header indicates it's SAM template**:
    * Transform: 'AWS::Serverless-2016-10-31'
* Write Code
    * AWS::Serverless::Function
    * AWS::Serverless::Api
    * AWS::Serverless::SimpleTable
* Package & Deploy:
    * aws cloudformation package / sam package
    * aws cloudformation deploy / sam deploy
    
---

## Deep dive into SAM deployment
* aws cloudformation package
* aws cloudformation deploy

### Diagram
[<img src="https://i.imgur.com/IX4bcxh.png">](https://i.imgur.com/IX4bcxh.png)
