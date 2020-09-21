# Routing Policy - Latency

## Doc

## Acronym

## Introduction
* Redirect to the server that has the least latency close to us
* Super helpful when latency of users is a priority
* Latency is evaluated in terms of user to designated AWS Region
* Germany may be directed to the US (if that's the lowest latency)

### Map
[<img src="https://i.imgur.com/7RgDv8u.png">](https://i.imgur.com/7RgDv8u.png)

### Demo
* New record
  * Name: latency.testappweb.com
  * Type: A
  * Alias: LB-ca-central
  * Routing Policy: Latency
  * Region: ca-central-1
  * Set ID: ca-central
  
* Idem for us-east with own values

[<img src="https://i.imgur.com/UO69Mjq.png">](https://i.imgur.com/UO69Mjq.png)
[<img src="https://i.imgur.com/dLQhw35.png">](https://i.imgur.com/dLQhw35.png)

* Test browser:

[<img src="https://i.imgur.com/z4UIUKl.png">](https://i.imgur.com/z4UIUKl.png)
[<img src="https://i.imgur.com/RinDI0u.png">](https://i.imgur.com/RinDI0u.png)
