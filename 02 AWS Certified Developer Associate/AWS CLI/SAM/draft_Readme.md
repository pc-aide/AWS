# SAM

## Doc
* [SAM CLI Install](https://docs.aws.amazon.com/serverless-application-model/latest/developerguide/serverless-sam-cli-install-linux.html)

## Prereq
    1. Homebrew
    2. SAM CLI

````bash
#Verify that Homebrew is installed
brew --version

# SAM CLI
sam --version
````

## Switchs
* sam build - Fetch dependencies & create local deployment artifacts
* sam package - Pakcge & upload to S3, generate CF template
* sam deploy - Deploy to CloudFormation

## Examples
### 01 Init - create project
````bash
sam init --runtime python3.7
````
[<img src="https://i.imgur.com/JeKBAT4.png">](https://i.imgur.com/JeKBAT4.png)

### 02 Build
````bash
sam build
````
[<img src="https://i.imgur.com/FpG1Rwe.png">](https://i.imgur.com/FpG1Rwe.png)

### 03 Deploy
````bash
sam deploy --guided
````
[<img src="https://i.imgur.com/HcVTJcz.png">](https://i.imgur.com/HcVTJcz.png)

