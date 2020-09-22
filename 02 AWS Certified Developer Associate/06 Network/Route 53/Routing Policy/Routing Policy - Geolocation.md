# Routing Policy - Geolocation

## Doc

## Acronym

## Introduction
* Different from Latency based!
* This routing based on user location
* Here we specify: traffic from the UK should go to this specific IP
* Should create a "default" policy (in case there's no match on location)


### Map
[<img src="https://i.imgur.com/x7fDw5l.png">](https://i.imgur.com/x7fDw5l.png)

### Demo
* Create Record Set
    * Name: Geo...
    * Type: A
    * TTL: 60s (for demo)
    * Value: 18.207.142.154 (us)
    * Routing Policy: geo...
    * Location: United States
    * Set ID: Geo-US
    
[<img src="https://i.imgur.com/hM92NPq.png">](https://i.imgur.com/hM92NPq.png)

* Idem for 2x anothers Geo:
* chose a Location : Default : ca

[<img src="https://i.imgur.com/wYqixkV.png">](https://i.imgur.com/wYqixkV.png)
[<img src="https://i.imgur.com/NJn8Mtx.png">](https://i.imgur.com/NJn8Mtx.png)

### Browser
[<img src="https://i.imgur.com/h8QtzxX.png">](https://i.imgur.com/h8QtzxX.png)
[<img src="https://i.imgur.com/q83BWWj.png">](https://i.imgur.com/q83BWWj.png)

* <aybe too high my latency (124ms) for Fr !?

[<img src="https://i.imgur.com/icxwVn8.png">](https://i.imgur.com/icxwVn8.png)
