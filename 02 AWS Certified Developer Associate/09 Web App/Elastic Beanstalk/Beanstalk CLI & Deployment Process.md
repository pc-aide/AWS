# Beanstalk CLI & Deployment Process

## Doc
* [Install the EB CLI](https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/eb-cli3-install.html)
* [elasticbeanstalk](https://docs.aws.amazon.com/cli/latest/reference/elasticbeanstalk/index.html)

## Acronym

## Intro
* We can install an additional CLI called the "EB cli" which makes working with Beanstalk from the CLI easier
* Basic commands are:
    * eb create
    * eb status 
    * eb health
    * eb events
    * eb logs
    * eb open
    * eb deploy
    * eb config
    * eb terminate
* It's helpful for your automated deployment pipelines

---

## Beanstalk Deployment Process
* Describe dependencies
    * (requirements.txt for Python, package.json for Node.js)
* Package code as zip, & describe dependencies
    * Python: requirements.txt
    * Node.js: package.json
* Console: upload zip file (create new app version), & then deploy
* CLI: create new app version using CLI (uploads zip), & then deploy
* Beanstalk will deploy the zip on each EC2 instance, resolve dependencies & start the application
