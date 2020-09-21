# Routing Policy - Weighted

## Acronym

## Doc
* [https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/routing-policy.html#routing-policy-weighted]()

## Introduction
* Control the % of the requests that go to specific endpoint
* Helpful to test 1% of traffic on new app version for example
* Helpful to split traffic between two regions
* Can be assocaited with Health Checks
* We can take the same Name (record set) & change only value or alias & weight


### Diagram
[<img src="https://i.imgur.com/wZOMLsV.png">](https://i.imgur.com/wZOMLsV.png)

### Demo
New record (A)
  * Name wighted.\<rootdomain\>.com
  * Alias : yes -> LB-ca-central
  * Weight: 50
  * Set ID: ca-central
  
* idem for us-east, just alias & set id differents

[<img src="https://i.imgur.com/6jThYLr.png">](https://i.imgur.com/6jThYLr.png)
[<img src="https://i.imgur.com/wyCVhw7.png">](https://i.imgur.com/wyCVhw7.png)

* Route 53 (cfg):

[<img src="https://i.imgur.com/c2lNLYY.png">](https://i.imgur.com/c2lNLYY.png)

* Browser:

[<img src="https://i.imgur.com/DJSS5ou.png">](https://i.imgur.com/DJSS5ou.png)
[<img src="https://i.imgur.com/waHYOQk.png">](https://i.imgur.com/waHYOQk.png)
