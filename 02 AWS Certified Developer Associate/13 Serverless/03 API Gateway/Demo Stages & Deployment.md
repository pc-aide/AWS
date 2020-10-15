# Demo Stages & Deployment

## Doc

## Acronym

## Intro
* Lambda-APIGW-Proxy\Edit code:
  * body = ""Test from Lambda v1 
  * Publish new version
  
[<img src="https://i.imgur.com/DVJGUS5.png">](https://i.imgur.com/DVJGUS5.png)
[<img src="https://i.imgur.com/eRGRPhk.png">](https://i.imgur.com/eRGRPhk.png)

* $LATEST\Edit code:
  * body: "v2"
  * publish
  
[<img src="https://i.imgur.com/q2jKgtC.png">](https://i.imgur.com/q2jKgtC.png)

* Create Alias
    * Name: DEV
    * Version: $LATEST
* 2<sup>nd</sup> alias:
    * Name: TEST
    * Version: 2
* 3<sup>rd</sup> alias:
    * Name: PROD
    * Version: 1
    
[<img src="https://i.imgur.com/01rKPWH.png">](https://i.imgur.com/01rKPWH.png)
    
* API Gateway\Resources
    * /GET
    * Change API
    
[<img src="https://i.imgur.com/2546iQ3.png">](https://i.imgur.com/2546iQ3.png)

* Root\**create resource**
    * Resource name: StageVariables
    
[<img src="https://i.imgur.com/fR5jKg1.png">](https://i.imgur.com/fR5jKg1.png)

* create **GET method** to /stagevariables
    * CheckBox: Use Lambda Proxy integration
    * Lambda function: Lambda-APIGW-Proxy:${stageVariables.lambdaAlias}
    
[<img src="https://i.imgur.com/SzDIPQY.png">](https://i.imgur.com/SzDIPQY.png)
[<img src="https://i.imgur.com/EObt5F9.png">](https://i.imgur.com/EObt5F9.png)

* Lambda (version 2)\permission
    * Resource-based policy empty
    
[<img src="https://i.imgur.com/bCfHaPC.png">](https://i.imgur.com/bCfHaPC.png)

* AWS CLI
    * change : ${stageVa...} for DEV:
````bash
aws lambda add-permission   --function-name "arn:aws:lambda:us-east-1:427263915585:function:Lambda-APIGW-Proxy:DEV"   --source-arn "arn:aws:execute-api:us-east-1:427263915585:ps7zttc39h/*/GET/stagevariables"   --principal apigateway.amazonaws.com   --statement-id fa5f2af6-590d-4f62-b11b-051a0d2a9fb6   --action lambda:InvokeFunction --region us-east-1
````

[<img src="https://i.imgur.com/NXyB3WI.png">](https://i.imgur.com/NXyB3WI.png)

* same thing for **TEST, PROD**
````bash
aws lambda add-permission   --function-name "arn:aws:lambda:us-east-1:427263915585:function:Lambda-APIGW-Proxy:TEST"   --source-arn "arn:aws:execute-api:us-east-1:427263915585:ps7zttc39h/*/GET/stagevariables"   --principal apigateway.amazonaws.com   --statement-id fa5f2af6-590d-4f62-b11b-051a0d2a9fb6   --action lambda:InvokeFunction --region us-east-1
````

[<img src="https://i.imgur.com/M1UL3NR.png">](https://i.imgur.com/M1UL3NR.png)
[<img src="https://i.imgur.com/CpmBEP5.png">](https://i.imgur.com/CpmBEP5.png)

* F5 Lambda-APIGW-Proxy (Alias:PROD)\Permissions\
    * Resources-based policy
    * IDEM : TEST, DEV
    
[<img src="https://i.imgur.com/XpzqHGQ.png">](https://i.imgur.com/XpzqHGQ.png)
[<img src="https://i.imgur.com/DaoMZDF.png">](https://i.imgur.com/DaoMZDF.png)
[<img src="https://i.imgur.com/IPIiILX.png">](https://i.imgur.com/IPIiILX.png)

* API Gateway\**popup**\ok

[<img src="https://i.imgur.com/8xpPWbY.png">](https://i.imgur.com/8xpPWbY.png)
[<img src="https://i.imgur.com/QkDSESk.png">](https://i.imgur.com/QkDSESk.png)

* Test
    * **Stage Variables**
    * lambdaAlias: DEV, TEST, PROD
    
[<img src="https://i.imgur.com/aBiSpNo.png">](https://i.imgur.com/aBiSpNo.png)
[<img src="https://i.imgur.com/92ZX3C7.png">](https://i.imgur.com/92ZX3C7.png)
[<img src="https://i.imgur.com/wjAi9Or.png">](https://i.imgur.com/wjAi9Or.png)
[<img src="https://i.imgur.com/Njza9qb.png">](https://i.imgur.com/Njza9qb.png)
[<img src="https://i.imgur.com/6D9ssSR.png">](https://i.imgur.com/6D9ssSR.png)
[<img src="https://i.imgur.com/eWnC58M.png">](https://i.imgur.com/eWnC58M.png)
[<img src="https://i.imgur.com/GAFDA79.png">](https://i.imgur.com/GAFDA79.png)
[<img src="https://i.imgur.com/UatE9SG.png">](https://i.imgur.com/UatE9SG.png)

* API Gateway\Action\**Deploy API**
    * Deployment stage: dev

[<img src="https://i.imgur.com/S8QFjfD.png">](https://i.imgur.com/S8QFjfD.png)
[<img src="https://i.imgur.com/BoD0aUr.png">](https://i.imgur.com/BoD0aUr.png)

* Stage variables\**add stage variables**
    * name: lambdaAlias
    * value: DEV

[<img src="https://i.imgur.com/cnpgOcR.png">](https://i.imgur.com/cnpgOcR.png)
[<img src="https://i.imgur.com/X1VxQne.png">](https://i.imgur.com/X1VxQne.png)

* deploy new api
    * Resource\Action\Deploy API
      * Deployment stage: new stage
      * Stage name: TEST
* Stage variables
    * name: lambdaalias
    * value: TEST
      
[<img src="https://i.imgur.com/6zdX51E.png">](https://i.imgur.com/6zdX51E.png)
[<img src="https://i.imgur.com/zJZZjWH.png">](https://i.imgur.com/zJZZjWH.png)

* 3<sup>rd</sup> stage:
    * stage name: PROD
    * Deployment: recent
* stage variables
    * name: lambdaAlias
    * value: PROD
    
[<img src="https://i.imgur.com/OjVquBL.png">](https://i.imgur.com/OjVquBL.png)
[<img src="https://i.imgur.com/gblzuJt.png">](https://i.imgur.com/gblzuJt.png)

* Browswer
    * PROD -> path
    * TEST,DEV
    
[<img src="https://i.imgur.com/YPb1GP0.png">](https://i.imgur.com/YPb1GP0.png)
[<img src="https://i.imgur.com/ODJ7UCa.png">](https://i.imgur.com/ODJ7UCa.png)
[<img src="https://i.imgur.com/rL7l67c.png">](https://i.imgur.com/rL7l67c.png)
