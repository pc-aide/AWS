# Security Groups
* Act as bult-in firewalls
* Control
	* Accessibility to instance
	* Traffic (allow or deny)

## NB
* 0.0.0.0, ::/0 - all IP addresses (allow they entire internet)

## Acronym
* sg - Security Group
* VPC - Virtual Private Cloud
* ISP - Internet Service Provider

## Doc
* [EC2 Security groups for Linux instances](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-security-groups.html?icmpid=docs_ec2_console#creating-security-group)

## Topology
[<img src="https://i.imgur.com/V0nk7kY.png">](https://i.imgur.com/V0nk7kY.png)

## AWS Console
* EC2\Network & Security\Security Groups

[<img src="https://i.imgur.com/xtDozF6.png">](https://i.imgur.com/xtDozF6.png)

### Create Security group
#### 1st step (ObjectName + VPC)
1) Name
2) Description
3) VPC

#### 2th step (Inbound & Outbount)
4) Inbound

	* Type
		* HTTP, SSH, ICMPv4, RDP
	* Protocol
		* Echo Reply, TCP, UDP
	* Port 
		* 53, 22,23, 80, 443,3389 ,8080
	* Source
		* Custom
		* Anywhere
		* My IP
			* what is my ISP (IPv4 Public)
	* Description


[<img src="https://i.imgur.com/zf2ZKdt.png">](https://i.imgur.com/zf2ZKdt.png)

* Default
	* Inbound : all Inoubound traffic is denied
	* Outbound : all Outbound traffic is allowed
	
[<img src="https://i.imgur.com/RqUipAc.png">](https://i.imgur.com/RqUipAc.png)

[<img src="https://i.imgur.com/oJbKzgH.png">](https://i.imgur.com/oJbKzgH.png)
