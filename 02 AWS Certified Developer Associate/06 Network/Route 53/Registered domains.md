# Registered domains

## Doc

## Acronym

## Registered domains
* about 15min before it's ready to used

[<img src="https://i.imgur.com/t9z2lon.png">](https://i.imgur.com/t9z2lon.png)

### Hosted zone
* it will create automatic in your hosted zone

[<img src="https://i.imgur.com/FYi8NVP.png">](https://i.imgur.com/FYi8NVP.png)
[<img src="https://i.imgur.com/1RwyI3q.png">](https://i.imgur.com/1RwyI3q.png)

### nslookup
[<img src="https://i.imgur.com/GOq5J1J.png">](https://i.imgur.com/GOq5J1J.png)

* after 15min with email as confirmation:

[<img src="https://i.imgur.com/DPnYF86.png">](https://i.imgur.com/DPnYF86.png)

### Create record set
* ALB (alias)

[<img src="https://i.imgur.com/eIG73V4.png">](https://i.imgur.com/eIG73V4.png)

* nslookup:

[<img src="https://i.imgur.com/EIght0z.png">](https://i.imgur.com/EIght0z.png)

* Browser:

[<img src="https://i.imgur.com/DOiFzYk.png">](https://i.imgur.com/DOiFzYk.png)


## Cons
* if you delete your hosted zone (ex. domain1.com) of own registered domain (buy from AWS) - it's not very quick to rebuild for new IP/LB, for hosted zone

* hosted zones:
* 172800 (TTL) / 60 = 2880 min = 48 h = **2 j**
* we pay each item record in a hosted zone
* idem if we try with alias (A) - nothing

[<img src="https://i.imgur.com/5b6D2hm.png">](https://i.imgur.com/5b6D2hm.png)
[<img src="https://i.imgur.com/3qMzlxl.png">](https://i.imgur.com/3qMzlxl.png)
[<img src="https://i.imgur.com/5luoVq7.png">](https://i.imgur.com/5luoVq7.png)

* nslookup servFail

[<img src="https://i.imgur.com/1htmGvB.png">](https://i.imgur.com/1htmGvB.png)
[<img src="https://i.imgur.com/8Kpnx0S.png">](https://i.imgur.com/8Kpnx0S.png)

* Browser:

[<img src="https://i.imgur.com/6t4rpjN.png">](https://i.imgur.com/6t4rpjN.png)
[<img src="https://i.imgur.com/XuP9gWM.png">](https://i.imgur.com/XuP9gWM.png)
[<img src="https://i.imgur.com/b4msRCO.png">](https://i.imgur.com/b4msRCO.png)


* versus from other domain register - quick respond if change IP
  * Godaddy
  
