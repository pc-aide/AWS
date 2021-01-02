# ALB

## Acronym
* ALB - Application Load Balancer
* AZ - Availability Zone
* LB - Load Balancer
* SG - Security Group

## Abbreviation
* cfg - configuration

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
  
### 02 - cfg Security Settings/SG
* Choose at least one SG for ALB
