# CodeDeploy

## Acronym
* SAM - Serverless Application Model

## Doc

## Intro
* **CodeDeploy** can help you automate traffic shift for Lambda aliases
* Feature is integrated within the SAM framework
* **Linear**: grow traffic every N minutes until 100%
    * Linear10PercentEvery3Minutes
    * Linear10PercentEvery10Minutes
* **Canary**: try X percent then 100%
    * Canary10Percent5Minutes
    * Canary10Percent30Minutes
* **AllAtOnce**: immediate
* Can create Pre & Post Traffic hooks to check the health of the Lambda function

### Diagram 
[<img src="https://i.imgur.com/TFpAOyd.png">](https://i.imgur.com/TFpAOyd.png)
