# IP Addressing Globomantics VPC Design

## Prefix
* Pub - Public
* Priv - Private

## VPC Design
* Region: us-east-1
* AZs:
  * us-east-1a
  * us-east-1b
  * us-east-1c
* Subnets
  * AZs:
    * us-east-1a
      * Subnet-1-Pub-10.0.1.0/24
      * Subnet-4-Priv-10.0.4.0/24
    * us-east-1b
      * Subnet-2-Pub-10.0.2.0/24
      * Subnet-5-Priv-10.0.5.0/24
    * us-east-1c
      * Subnet-3-Pub-10.0.3.0/24
      
### Diagram
[<img src="https://i.imgur.com/tYweZH2.png">](https://i.imgur.com/tYweZH2.png)

---

## basic-network.template
* https://github.com/pc-aide/AWS/blob/master/01%20AWS%20Certified%20Solutions%20Architect%20-%20Professional/CloudFormation/Template/basic-network.md

---

## IP addressing
* Other CIDR
  * 10.1.0.0/24
  
### Diagram
[<img src="https://i.imgur.com/RaWcMXy.png">](https://i.imgur.com/RaWcMXy.png)
