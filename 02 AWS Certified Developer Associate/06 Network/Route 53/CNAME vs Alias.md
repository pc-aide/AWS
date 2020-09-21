# CNAME vs Alias

## Doc

## Acronym
* LB - Load Balancing)
* ALB - Application Load Balancing

## Introduction
* AWS Resources (LB, CloudFront...) expose an AWS hostname:
    * **LB01-1234.ca-central-1.ELB.amazonaws.com** & you want **MyApp.MyDomain.com**
      * CNAME: 
          * Points a hostname to any other hostname (app.myDomain.com => blabla.anything.com)
          * <ins>Only for non root domain (ex.Something.MyDomain.com)</ins>
      * Alias: 
          * Points a hostname to an AWS Resource (app.MyDomain.com => blabla.amazonaws.com)
          * <ins>Works for Root domain & non root domain (aka mydomain.com)
          * Free of charge
          * Native health check

---
   
## Demo CNAME & LB
* Create a ALB
* Check if healthy

[<img src="https://i.imgur.com/nbKOHLA.png">](https://i.imgur.com/nbKOHLA.png)
[<img src="https://i.imgur.com/4pa2Gui.png">](https://i.imgur.com/4pa2Gui.png)

* Route 53\ record:
   * CNAME
      * Name: lb.\<rootDomain\>.com
      * value: DNS.Name
      
[<img src="https://i.imgur.com/FZtNAMV.png">](https://i.imgur.com/FZtNAMV.png)
[<img src="https://i.imgur.com/b16c0Ad.png">](https://i.imgur.com/b16c0Ad.png)

* Test: Browser:

[<img src="https://i.imgur.com/JX3QQH0.png">](https://i.imgur.com/JX3QQH0.png)

---

## Used Alias
[<img src="https://i.imgur.com/4l9k0Yb.png">](https://i.imgur.com/4l9k0Yb.png)
[<img src="https://i.imgur.com/NweeURK.png">](https://i.imgur.com/NweeURK.png)
