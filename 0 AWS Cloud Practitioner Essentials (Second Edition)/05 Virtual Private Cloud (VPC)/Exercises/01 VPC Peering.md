# E.g.
[<img src="https://i.imgur.com/n4M5BDJ.png">](https://i.imgur.com/n4M5BDJ.png)

## Demo
[<img src="https://i.imgur.com/l4oLe11.png">](https://i.imgur.com/l4oLe11.png)
[<img src="https://i.imgur.com/b7u7yjJ.png">](https://i.imgur.com/b7u7yjJ.png)
* Idem AZ
* No ping between 2 hosts
  * Event if wf.msc\{inbound,outbound} enabled ICMPv4
   * Because it's firewall -> aws security-group
    * Only RDP (SG : Inbound.RDP & Oubound all traffic)
      * Solution: sg-ICMPv4_Inbount_Request (echo) + VPC peering connection

## Goal
1) Enable ping between 2x EC2

### Visio (draft)
[<img src="https://i.imgur.com/hTeLcqI.png">](https://i.imgur.com/hTeLcqI.png)
