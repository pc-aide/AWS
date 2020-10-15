# Stages & deployment

## Doc

## Acronym
* ARN - Amazon Resource Name

## Deployment Stages
* Making changes in the API Gateway does not mean they're effective
* You need to make a "deployment" for the mto be in effect
* It's a common source of confusion
* Changes are deployed to "Stages" (as many as you want)
* Use the naming you like for stages (dev, test, prod)
* Each stage has its own configuration parameters
* Stages can be rolled back as a history of deplyments is kept

---

## Stages v1 & v2 API breaking change
[<img src="https://i.imgur.com/U480wY6.png">](https://i.imgur.com/U480wY6.png)

---

## Stage Variables
* Stage variables are like environment variables for API Gateway
* Use them to change often changing configuration values
* They can be used in:
    * Lambda function ARN
    * HTTP Endpoint
    * Parameter mapping templates
* Use cases:
    * Configure HTTP endpoints your stages talk to (dev,test,prod...)
    * Pass configuration parameters to Lambda through mapping templates
* Stage variables are passed to the "context" object in Lambda

---

## Stage Variables & Lambda Aliases
* We create a **stage variable** to indicate the corresponding Lambda alias
* Our API gateway will automatically invoke the right Lambda function

### Diagram
[<img src="https://i.imgur.com/VgBYIMs.png">](https://i.imgur.com/VgBYIMs.png)
