# Best Practices

## Acronym
* KMS - Key Managment Service

## Doc

## Intro
* Perform heavy-duty work outside of your function handler   
    * Connect to db outside of your function handler
    * Initialize the AWS SDK outside of your function handler
    * Pull in dependencies of datasets outside of your function handler
* Use env variables for:
    * Database Connection Strings, S3 bucket, etc... don't put these values in your code
    * Passwords, sensitive values... they can be encrypted using KMS
* Minimize your deployment package size to its runtime necessities
    * Break down the function if need be
    * Remember the AWS Lambda limits
    * Use Layers where necessary
* Avoid using recursive code, never have a Lambda function call itself
