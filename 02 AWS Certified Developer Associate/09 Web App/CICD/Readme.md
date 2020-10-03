# CI/CD

## Acroym
* CI/CD - Continuous Integration, Continuous Delivery
* EB - Elastic Beanstalk

## Doc

## Intro
* We now know how to create resources in AWS manually (Fundamentals)
* We know how to intect with AWS programmatically (CLI)
* We've seen how to deploy code to AWS using EB
* All these manual steps make it very likely for us to do mistakes
* What we'd like is to push our code "in a repository" & have it deployed onto the AWS
    * Automatically
    * The right way
    * Making sure it's testd before deploying 
    * With possibility to go into different stages (dev, test, pre-prod, prod)
    * With manual approval where needed
* To be a proper AWS developer... we need to lear AWS CI/CD
* This section is all about automating the deployment we've done so far while adding incrased safety
* It correspond to a whole part of the AWS Certification
* We'll lear about
    * AWS CodeCommit: storing our code
    * AWS CodePipeline: automating our pipeline from code to EB
    * AWS CodeBuild: building & testing our code
    * AWS CodeDeploy: deploying the code to EC2 fleets (not Beanstalk)
    
---

## Continuous Integration
* Developers push the ocde to a code repository often:
    * GitHub/
    * CodeCommit
    * Bitbucket
    * etc...
* A testing/build server checks the code as soon as it's pushed
    * CodeBuild
    * Jenkins CI
    * etc
* The developer gets feedback about the tests & checks taht have passed/failed
* Find bugs early, fix bugs
* Deliver faster as the code is tested
* Deploy often
    
### Diagram
[<img src="https://i.imgur.com/FiUM5JQ.png">](https://i.imgur.com/FiUM5JQ.png)

---

## Continuous Delivery
* Ensure that the software can be released reliably whenever needed
* Ensure deployments happen often & are quick
* Shift away from "one release every 3 months" to "5 realases a day"
* That usually means automated deployment
    * CodeDeploy
    * Jenkins CD
    * Spinnaker
    * Etc...
    
### Diagram
[<img src="https://i.imgur.com/E0WEIoT.png">](https://i.imgur.com/E0WEIoT.png)

---

## Technology Stack for CI/CD
* 5 steps
    1) Code
      * AWS CodeCommit & GiHub or 3rd party code repository
    2) Build
      * AWS CodeBuild & Jenkins CI or 3rd party CI servers
    3) Test
      * AWS CodeBuild & Jenkins CI or 3rd party CI servers
    4) Deploy 
      * AWS EB & AWS CodeDeploy
    5) Provision
      * AWS EB & User Managed EC2 Instance Fleet (CloudFormation)
    
### Diagram
[<img src="https://i.imgur.com/nJedyh3.png">](https://i.imgur.com/nJedyh3.png)
