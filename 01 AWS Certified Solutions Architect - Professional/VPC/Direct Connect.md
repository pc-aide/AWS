# Direct Connect

## Acronym
* DX - Direct Connection
* ISP - Internet Service Provider
  * e.g: Bell, Videotron, Telus, and so on
* LAG - Link Aggregation Groups

## Intro
* Private connection to AWS network
  * Dont' cross the public internet
  * Dedicated direct link between your network & network AWS
* Consistent network experience 
* Connect to AWS services or VPC in any region
* Multiple physical connection options   
* Multiple port speeds

---

## Physical Connection Options
1) Circuit between customer location & DX location
2) Curcuit between customer location & ISP offering DX
3) Customer router in same location as DX router
* Port speeds
  * 1Gb or 10Gb dedicated ports
  * Sub 1Gb on hosted connection
* LAG supported for dedicated ports
  * 40Gb dedicated ports
  
---

## Performance & Availability
* Expensive:
  * Redundancy

[<img src="https://i.imgur.com/IdSzrPL.png">](https://i.imgur.com/IdSzrPL.png)

* Less expensive:

[<img src="https://i.imgur.com/cJnCIT9.png">](https://i.imgur.com/cJnCIT9.png)
