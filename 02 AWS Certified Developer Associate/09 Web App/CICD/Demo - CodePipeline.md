# Demo - CodePipeline

## Acronym
* EB - Elastic Beanstalk

## Doc
* [What is AWS CodePipeline?](https://docs.aws.amazon.com/codepipeline/latest/userguide/welcome.html)

## Intro
* CodeCommit\Pipeline\Getting started\Create pipeline
    * Pipeline name: Pipeline-Demo
    
[<img src="https://i.imgur.com/JulPTYY.png">](https://i.imgur.com/JulPTYY.png)

* Source
    * Source provider: CodeCommit
    * Repository name: nodejs-app
    * Branch name: master

[<img src="https://i.imgur.com/45Z5k7K.png">](https://i.imgur.com/45Z5k7K.png)

* Skip build stage

[<img src="https://i.imgur.com/m43a5l2.png">](https://i.imgur.com/m43a5l2.png)

* Deploy
    * Deploy provider: AWS EB
    * Application name: WebApp-Beanstalk
    * Environment name (from your EB): WebAppBeanstalkDemo-env
    
[<img src="https://i.imgur.com/ekxVIn7.png">](https://i.imgur.com/ekxVIn7.png)

* Next & create pipeline

[<img src="https://i.imgur.com/NH3zzCB.png">](https://i.imgur.com/NH3zzCB.png)

* update your code:
````bash
git clone <https>
````
[<img src="https://i.imgur.com/iGunSLt.png">](https://i.imgur.com/iGunSLt.png)

* ex: update background index.html:

[<img src="https://i.imgur.com/gSzAPAu.png">](https://i.imgur.com/gSzAPAu.png)

* status
````bash
git status
````
[<img src="https://i.imgur.com/ukvcONe.png">](https://i.imgur.com/ukvcONe.png)

* add
````bash
git add .
````
[<img src="https://i.imgur.com/gc9A9oP.png">](https://i.imgur.com/gc9A9oP.png)

* commit
````bash
git commit -m "update index.html with background red"
````
[<img src="https://i.imgur.com/4A9xh4w.png">](https://i.imgur.com/4A9xh4w.png)

* push
````bash
git push
````

[<img src="https://i.imgur.com/IH68UUe.png">](https://i.imgur.com/IH68UUe.png)

* pipeline (in progress):

[<img src="https://i.imgur.com/VURWieb.png">](https://i.imgur.com/VURWieb.png)
[<img src="https://i.imgur.com/M28iqDr.png">](https://i.imgur.com/M28iqDr.png)

* Browser + F5:

[<img src="https://i.imgur.com/EiqvFZU.png">](https://i.imgur.com/EiqvFZU.png)

* EB\Running version (Pipeline):

[<img src="https://i.imgur.com/IYv7uCL.png">](https://i.imgur.com/IYv7uCL.png)

* EB\Application versions:

[<img src="https://i.imgur.com/1YRJKEn.png">](https://i.imgur.com/1YRJKEn.png)

* Pipeline\Edit:

[<img src="https://i.imgur.com/Ld4V4or.png">](https://i.imgur.com/Ld4V4or.png)

* Deploy\ + Add stage:

[<img src="https://i.imgur.com/X4gIyrs.png">](https://i.imgur.com/X4gIyrs.png)

* Add stage
    * stage name: Deploy-To-Prod
    
* Deploy-To-Prod\ + Add action group:
    * Acion name: Manual-Approval
    * Action provider: Manual approval
    * Done
    
[<img src="https://i.imgur.com/MGCw9Xl.png">](https://i.imgur.com/MGCw9Xl.png)

* Add second action group (Deploy-To-Prod)\
    * Action name: Deploy-To-Prod-Beanstalk
    * Action provider: AWS Elastic Beanstalk
    * Input artifacts: SourceArtifact
    * Application name: Web-App-Beanstalk-Demo
    * Environment name: WebAppBeanstalkDemo-Prod

[<img src="https://i.imgur.com/UJ4AyaY.png">](https://i.imgur.com/UJ4AyaY.png)

* workflow:

[<img src="https://i.imgur.com/J9MzVNk.png">](https://i.imgur.com/J9MzVNk.png)

* if our testing new workflow:
* update background yellow -> index.html

[<img src="https://i.imgur.com/KCxsVUj.png">](https://i.imgur.com/KCxsVUj.png)

* Browswer (prod): 

[<img src="https://i.imgur.com/Fnx1yVW.png">](https://i.imgur.com/Fnx1yVW.png)

* not running: 

[<img src="https://i.imgur.com/h6etMnN.png">](https://i.imgur.com/h6etMnN.png)

* edit CodeCommit\Code\index.html
    * background: pink
    
[<img src="https://i.imgur.com/KT2NeN1.png">](https://i.imgur.com/KT2NeN1.png)
[<img src="https://i.imgur.com/KnygNsP.png">](https://i.imgur.com/KnygNsP.png)

* workflow (pipeline):

[<img src="https://i.imgur.com/r0qZZjs.png">](https://i.imgur.com/r0qZZjs.png)

* wainting for approval:

[<img src="https://i.imgur.com/aQhJDV3.png">](https://i.imgur.com/aQhJDV3.png)

* Browser
    1) (blue-prod):
    2) (pink-root)

[<img src="https://i.imgur.com/Suh2eZy.png">](https://i.imgur.com/Suh2eZy.png)
[<img src="https://i.imgur.com/WvDp9Mm.png">](https://i.imgur.com/WvDp9Mm.png)

* Pipeline\Review:

[<img src="https://i.imgur.com/U3nQo9H.png">](https://i.imgur.com/U3nQo9H.png)

* Approve:

[<img src="https://i.imgur.com/ymeswW1.png">](https://i.imgur.com/ymeswW1.png)

* workflow with approved:

[<img src="https://i.imgur.com/K2q5Yme.png">](https://i.imgur.com/K2q5Yme.png)

* workflow done (pipeline):

[<img src="https://i.imgur.com/3Mo0Ggg.png">](https://i.imgur.com/3Mo0Ggg.png)

* Browswer:

[<img src="https://i.imgur.com/37o6ZwC.png">](https://i.imgur.com/37o6ZwC.png)
