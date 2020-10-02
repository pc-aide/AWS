# Beanstalk Second Envrionment

## Acronym
* HA - High Availability
* AZ - Availability Zone
* PRD - Production

## Doc
* [Web server environments](https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/concepts-webserver.html?icmpid=docs_elasticbeanstalk_console)
* [Worker environments](https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/concepts-worker.html?icmpid=docs_elasticbeanstalk_console)

## Intro
* Create second new environment\Web server env
    * Environment name: DemoBeanStalk-prod
    * Domain: App-Demo-In-Prod
    * Description: BeanStalk app in prod
    * Platform: Node.js
    * Configure more options

[<img src="https://i.imgur.com/mRu6Hye.png">](https://i.imgur.com/mRu6Hye.png)
[<img src="https://i.imgur.com/RWhAsDO.png">](https://i.imgur.com/RWhAsDO.png)
[<img src="https://i.imgur.com/SXXy72Z.png">](https://i.imgur.com/SXXy72Z.png)

* Configure DemoBeanstalk-prod
    * Configuratin preset: HA
    * Capacity\Edit
        * placement: all AZs
* Create envrionment
* It'll take ~5min to wait
        
[<img src="https://i.imgur.com/9Jnwtay.png">](https://i.imgur.com/9Jnwtay.png)
[<img src="https://i.imgur.com/CpDDcUF.png">](https://i.imgur.com/CpDDcUF.png)
[<img src="https://i.imgur.com/cRPwZiw.png">](https://i.imgur.com/cRPwZiw.png)

* Broswer
  * prod - HA
  * no-prd - no HA
  
[<img src="https://i.imgur.com/gHKRxvP.png">](https://i.imgur.com/gHKRxvP.png)

* EC2:

[<img src="https://i.imgur.com/f5swro0.png">](https://i.imgur.com/f5swro0.png)

* ELB:

[<img src="https://i.imgur.com/SGHihBc.png">](https://i.imgur.com/SGHihBc.png)

* EC2\Tags (check up- ex.: ASG ?=? Instance):

[<img src="https://i.imgur.com/q2T1vM4.png">](https://i.imgur.com/q2T1vM4.png)
[<img src="https://i.imgur.com/dh0HSJI.png">](https://i.imgur.com/dh0HSJI.png)
[<img src="https://i.imgur.com/SZ6XLTh.png">](https://i.imgur.com/SZ6XLTh.png)

* Default web server
      * nginx
      
[<img src="https://i.imgur.com/G9N2TzW.png">](https://i.imgur.com/G9N2TzW.png)
