# ALB

## Acronym
* ALB - Application Load Balancer
* AZ - Availability Zone
* LB - Load Balancer
* SG - Security Group
* SSL - Secure Sockets Layer
* TG - Target Group

## Abbreviation
* cfg - configuration

## Pricing calculator
* [Pricing_Calculator](https://aws.amazon.com/elasticloadbalancing/pricing/#Pricing_Calculator)

## Create new ALB
### 01 - cfg LB
1) Name: 
2) Scheme:
  * internet-facing - public (we can see on internet)
  * internal - private

3) IP address type
  * IPv4
  * dualtak - ipv4 & ipv6
4) Listerners

|n|LB Protocol|LB Port|
|-|-----------|-------|
|1|HTTP       |80     |


5) AZ
  * VPC: default
  * AZ: you have to two AZs
  
### 02-03 - cfg Security Settings/SG
1) Choose at least one SG for ALB

### 04 - cfg Routing
1) TG: new or existing TG
2) Target Type: 
  * instance
  * IP
  * Lambda function
3) Protocol
  * HTTP
  * HTTPS - need SSL here
4) Port
5) Health check
  * Protocol
    * HTTP
    * HTTPS
  * Path
6) Advanced health check settings (optiona)

### 05 - Register Targets
* Instances: add to registered

|n|Instance (i-\<Number\>)| on port|
|-|-----------------------|--------|
|1|i-\<number\>         | 80     |
