# NAT Gateways

## Acronym
* AZ - Availability Zone
* NAT - Network Address Translation
* HA - High Available
* SG - Security Group

## NAT
1) NAT gateway
  * HA per zone
  * Bandwidth up to 45Gbps
  * Managed by AWS
  * Charged by number of gateways, duration, & data transit
  * Port forwarding not supported
  * Bastion hosts not suported
  * SGs not supported
2) NAT instance
  * Use script to perform failOver
  * Bandwidth dependent on instance type
    * e.g -> t2.micro -> bandwidth -> **Low to Mederate**
  * Managed by you
  * Charged by number of instances, duration, & instance type/size
  * Port forwarding supported
  * Use as bastion host 
  * SGs supported

### Diagram
[<img src="https://i.imgur.com/qnViHlH.png">](https://i.imgur.com/qnViHlH.png)

---

## HA
### NAT-GW
* if NAT-GW fail, AWS will be create new NAT-GW, nothing to do as cumsumer or used multiple NAT-inst + detection failOver (applicance)

[<img src="https://i.imgur.com/huqGHqz.png">](https://i.imgur.com/huqGHqz.png)

### NAT-Inst
* if NAT-Inst fail, Client must have to update rtb quickly
* if NAT-Inst fail, script detect for update rtb on another AZ

[<img src="https://i.imgur.com/gRMv34e.png">](https://i.imgur.com/gRMv34e.png)
[<img src="https://i.imgur.com/kanhteD.png">](https://i.imgur.com/kanhteD.png)
[<img src="https://i.imgur.com/DGRorlV.png">](https://i.imgur.com/DGRorlV.png)
