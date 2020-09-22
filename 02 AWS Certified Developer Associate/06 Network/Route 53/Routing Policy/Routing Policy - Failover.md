# Routing Policy - Failover

## Doc

## Acronym

## Diagram
[<img src="https://i.imgur.com/hr14vy6.png">](https://i.imgur.com/hr14vy6.png)

### Demo
* 3x Health Checks
    * us-east
    * Paris
    * ca

[<img src="https://i.imgur.com/LliEwJs.png">](https://i.imgur.com/LliEwJs.png)

* Hosted zones
    * Root Domain: testwebaws.com - buy from AWS
    
[<img src="">]()

* Create Record Set:
  * Name: failover
  * Type: A
  * TTL: 60 (for demo)
  * Value: 35.180.228.120
  * Ruting Policy: Failover
  * Failver Record type: Primary
  * RadioButton: Yes (Associate with Health check)
  
[<img src="https://i.imgur.com/0SYjheS.png">](https://i.imgur.com/0SYjheS.png)

* Idem for our secondary:
* for secondary - don't need (optional) **associate with health check**

[<img src="https://i.imgur.com/35CMvYv.png">](https://i.imgur.com/35CMvYv.png)

* Browser:
