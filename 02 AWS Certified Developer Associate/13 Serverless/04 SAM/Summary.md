# Summary

## Acronym
* SAM - Serverless Application Model
* IAM - Identity & Access Management

## Doc

## Exam Summary
* SAM is built on CloudFormation
* SAM requires the **Transform** & **Resources** [`section-template.yaml`](#template.yaml)
* Commands to know:
    * **sam build**: fetch dependencies & create local deployment artifacts
    * sam package: package & upload to S3, generate CF template
    * **sam deploy**: deploy to CloudFormation
* SAM Policy templates for easy IAM policy defintion
* SAM is integrated with **CodeDeploy** to do deploy to Lambda alaises

### template.yaml
````yaml
cat template.yaml | grep 'Transform\|Resources'
````
[<img src="https://i.imgur.com/73SCGF6.png">](https://i.imgur.com/73SCGF6.png)
