# Demo Canary Deployments

## Acronym

## Doc

## Intro
* Lambda-PROD -> v1
* API Gateway\Resources
    * /GET
    * change **Integration Request**
    * Lambda function: Lambda-APIGW-Proxy**:1**
    
[<img src="https://i.imgur.com/cPTupIy.png">](https://i.imgur.com/cPTupIy.png)
[<img src="https://i.imgur.com/hg5uuC1.png">](https://i.imgur.com/hg5uuC1.png)
[<img src="https://i.imgur.com/YKoOZTV.png">](https://i.imgur.com/YKoOZTV.png)

* Deploy API
    * Deployment stage: PROD
* Browser
    * take couple seconds take to see v1
    
[<img src="https://i.imgur.com/hGVza3S.png">](https://i.imgur.com/hGVza3S.png)
[<img src="https://i.imgur.com/MECOOyo.png">](https://i.imgur.com/MECOOyo.png)
[<img src="https://i.imgur.com/Hh6nUwQ.png">](https://i.imgur.com/Hh6nUwQ.png)

* I want to test my v2 now
* Canary\**Create canary**
    * % of request directed to Canary: 50% (for demo)
    
[<img src="https://i.imgur.com/gJo1SuL.png">](https://i.imgur.com/gJo1SuL.png)

* Resources\
    * /GET\**Itegration Request**
    * Lambda function: version 2
    
[<img src="https://i.imgur.com/ctBambV.png">](https://i.imgur.com/ctBambV.png)

* Deploy API
    * Deployment stage: PROD (Canary Enabled)
    
[<img src="https://i.imgur.com/yy0xO50.png">](https://i.imgur.com/yy0xO50.png)

* Browser
    * version: 1 & 2 for PROD
    
[<img src="https://i.imgur.com/JUQW9oU.png">](https://i.imgur.com/JUQW9oU.png)
[<img src="https://i.imgur.com/IzGq8Ui.png">](https://i.imgur.com/IzGq8Ui.png)

* if i ok for this v2
* promote canary: update

[<img src="https://i.imgur.com/WJSQU7o.png">](https://i.imgur.com/WJSQU7o.png)
[<img src="https://i.imgur.com/B5lzzGG.png">](https://i.imgur.com/B5lzzGG.png)

* Browser
    * only v2
    
[<img src="https://i.imgur.com/RgrfKFT.png">](https://i.imgur.com/RgrfKFT.png)
