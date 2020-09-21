# CNAME vs Alias

## Doc

## Acronym
* LB - Load Balancing)

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
