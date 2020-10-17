# CodeDeploy

## Acronym
* SAM - Serverless Application Model
* CI/CD - Continuous Integration/ Continuous Delivery

## Doc
* [Tutorial: Deploying a Hello World application](https://docs.aws.amazon.com/serverless-application-model/latest/developerguide/serverless-getting-started-hello-world.html)

## Intro
* SAM framework natively uses CodeDeploy to update Lambda functions
* Traffic Shifting feature
* Pre & Post traffic hooks features to validate deployment (before the traffic shift start & after it ends)
* Easy & automated rollback using CloudWatch Alarms

### Diagram
[<img src="https://i.imgur.com/OHGpsbg.png">](https://i.imgur.com/OHGpsbg.png)

* Remove v1 

[<img src="https://i.imgur.com/vd9PuId.png">](https://i.imgur.com/vd9PuId.png)

---

## Demo
* Step 1 - Download a sample app
    * Choise 1
    * Project name
    * template: 1 Hello world 
````bash
sam init --runtime python3.7
````
[<img src="https://i.imgur.com/pdHqSeD.png">](https://i.imgur.com/pdHqSeD.png)

* Step 2 - Build your app
    * error: PythonPipBuilder
````bash
cd sam-app
sam build
````
[<img src="https://i.imgur.com/VfZcKFJ.png">](https://i.imgur.com/VfZcKFJ.png)

* change python3.7 -> 3.8
    * try again sam build

[<img src="https://i.imgur.com/knKTqsO.png">](https://i.imgur.com/knKTqsO.png)
[<img src="https://i.imgur.com/HbI3Xgg.png">](https://i.imgur.com/HbI3Xgg.png)

* add this to template.yaml
    * AutoPublishAlias: live
    * DeploymentPreference: live
      * Type: Canary10Percent10Minutes
        * gives me 2 versions
````bash
 Properties:
            Path: /hello
            Method: get
       AutoPublishAlias: live
       DeploymentPreference:
        Type: Canary10Percent10Minutes

Outputs:
````
* sam build again

[<img src="https://i.imgur.com/pg0gQbj.png">](https://i.imgur.com/pg0gQbj.png)

* Deploy package your app
````bash
sam deploy --guided
````
[<img src="https://i.imgur.com/vQ3knlc.png">](https://i.imgur.com/vQ3knlc.png)
[<img src="https://i.imgur.com/YmaBaW6.png">](https://i.imgur.com/YmaBaW6.png)

* Lambda:
    * https://i.imgur.com/YmaBaW6.png
    * application
      * Deployments
    
[<img src="https://i.imgur.com/2wiAwkt.png">](https://i.imgur.com/2wiAwkt.png)
[<img src="https://i.imgur.com/6tCydhV.png">](https://i.imgur.com/6tCydhV.png)
[<img src="https://i.imgur.com/Utet1E2.png">](https://i.imgur.com/Utet1E2.png)

* Lambda function
    * Qualifiers: version 1 & $LATEST
    
[<img src="https://i.imgur.com/VudJ4vK.png">](https://i.imgur.com/VudJ4vK.png)

* Test

[<img src="https://i.imgur.com/bUvGEc1.png">](https://i.imgur.com/bUvGEc1.png)

* Edit app.py
* "message": "hello world v2"
````python
 "body": json.dumps({
            "message": "hello world v2",
````

* re-package
````bahs
sam build
````
[<img src="https://i.imgur.com/1Cjup66.png">](https://i.imgur.com/1Cjup66.png)

* Deploy:
````bash
sam deploy --guided
````

[<img src="https://i.imgur.com/7AM0DVb.png">](https://i.imgur.com/7AM0DVb.png)

* yes changeSet
    * Delete Lambda Function (v2)
````text
 Add                     HelloWorldFunctionVersi   AWS::Lambda::Version      N/A                     
                          on6a32cf6766                                                                
* Modify                  HelloWorldFunctionAlias   AWS::Lambda::Alias        False                   
                          live                                                                        
* Modify                  HelloWorldFunction        AWS::Lambda::Function     False                   
- Delete                  HelloWorldFunctionVersi   AWS::Lambda::Version      N/A                     
                          on1be4d0258c  
````

* Lambda function 
    * version 1 Weight: 90%
    * version 2 Weight: 10%
    
[<img src="https://i.imgur.com/HS8BV4u.png">](https://i.imgur.com/HS8BV4u.png)

* CodeDeploy
    * Blue/green (deployment type)
    * Deployment status
    * it will take 10m (canary 10 minutes)
    
[<img src="https://i.imgur.com/GQN8IJV.png">](https://i.imgur.com/GQN8IJV.png)
[<img src="https://i.imgur.com/UK0sd2A.png">](https://i.imgur.com/UK0sd2A.png)

* after 10 minutes
    * traffic shifting
    * post-deployment validation

[<igm src="https://i.imgur.com/CVOyKh0.png">](https://i.imgur.com/CVOyKh0.png)

* Lambda
    * Alias: live (version 2)
    
[<img src="https://i.imgur.com/FhVdzLc.png">](https://i.imgur.com/FhVdzLc.png)
[<img src="https://i.imgur.com/LJt5gpn.png">](https://i.imgur.com/LJt5gpn.png)
