# 01 Singapore VS Seattle

## Goal
* Used CloudFront to accelerate (my application) that by **caching**
  content locally in an **edge location** that is close to me (USA)
  over the Pacific Ocean, here in **Seattle**

## My application
* Summary
1) Each request GET (http methods) - Seattle (84.17.41.25)
2) High latency 301 ms
3) IPv4 : Singapore (13.250.54.7)

[<img src="https://i.imgur.com/YxWY2MA.png">](https://i.imgur.com/YxWY2MA.png)


## Solution
1) Create a new CloudFront distribution : 

[<img src="https://i.imgur.com/gYV1mia.png">](https://i.imgur.com/gYV1mia.png)

2) Web :

[<img src="https://i.imgur.com/VNWO9xH.png">](https://i.imgur.com/VNWO9xH.png)

3) Cloud Distributions 

  * In progress : 
[<img src="https://i.imgur.com/jtduxxN.png">](https://i.imgur.com/jtduxxN.png)

  * Deployed :
  
[<img src="https://i.imgur.com/HqhLpY3.png">](https://i.imgur.com/HqhLpY3.png)

4) We need a domain up (ns lookup) ...
    * New registered domain - it will take 48h : 

[<img src="https://i.imgur.com/ZdPtvBA.png">](https://i.imgur.com/ZdPtvBA.png)


## nslookup
### Godaddy (working)
#### Browser
[<img src="https://i.imgur.com/b5KTm1P.png">](https://i.imgur.com/b5KTm1P.png)

### DNS Management
[<img src="https://i.imgur.com/5XAyALN.png">](https://i.imgur.com/5XAyALN.png)

````Bash
nslookup simpleapptest.online
````
* Server:		127.0.0.53
* Address:	127.0.0.53#53

* Non-authoritative answer:
* Name:	simpleapptest.online
* Address: 13.212.39.228

### Registered domains (AWS) no working
````Bash
nslookup sampleapplication.co.uk
````
* Server:		127.0.0.53
* Address:	127.0.0.53#53

** server can't find sampleapplication.co.uk: SERVFAIL

#### Hosted zones
[<img src="https://i.imgur.com/2MAFlFl.png">](https://i.imgur.com/2MAFlFl.png)
