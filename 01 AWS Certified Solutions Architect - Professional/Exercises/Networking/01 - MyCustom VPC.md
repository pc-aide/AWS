# 01 - My Custom VPC

## SRC
* https://youtu.be/VGAT5C8qIUY

## Topology
[<img src="https://i.imgur.com/1QuInkj.png">](https://i.imgur.com/1QuInkj.png)

## VPC
* Create VPC
 	* Name: MyCustomVPC
  * CIDR: 10.10.0.0/16
  * Tenancy: default
    
[<img src="https://i.imgur.com/dHyIXR6.png">](https://i.imgur.com/dHyIXR6.png)

## Subnets
### 01-Subnet
* Create Subnet
  * Name: PublicSubnet
  * VPC: MyCustomVPC
  * AZ: ca-central-1a
  * CIDR: 10.10.1.0/24
  * Auto-assign IPs: CheckBox IPv4
  
[<img src="https://i.imgur.com/FFQSnLW.png">](https://i.imgur.com/FFQSnLW.png)
[<img src="https://i.imgur.com/8LabVrt.png">](https://i.imgur.com/8LabVrt.png)

### 02-subnet
* Create subnet
  * Name: PrivateSubnet
  * VPC: MyCustomVPC
  * AZ: ca-central-1b
  * CIDR: 10.10.2.0/24
  
[<img src="https://i.imgur.com/GfNeU1l.png">](https://i.imgur.com/GfNeU1l.png)

## Internet Gateway
* Create Internet Gateway
	* Name: MyIGW
    * Attach to VPC: MyCustomVPC
    
[<img src="https://i.imgur.com/HQ2WWRG.png">](https://i.imgur.com/HQ2WWRG.png)

[<img src="https://i.imgur.com/B7itH7k.png">](https://i.imgur.com/B7itH7k.png)

## Route Tables
* Create Route Table
	* Name: MyRoute
    * VPC: MyCustomVPC
    * Edit Routes
    	* 0.0.0.0/0 | MyIGW
    * Edit subnet associations:
    	* CheckBox SubnetPublic
	
[<img src="https://i.imgur.com/IVFy9vP.png">](https://i.imgur.com/IVFy9vP.png)
[<img src="https://i.imgur.com/nXN9XWO.png">](https://i.imgur.com/nXN9XWO.png)
[<img src="https://i.imgur.com/NCowhgs.png">](https://i.imgur.com/NCowhgs.png)

## Instances
### EC2W19-01
* Launch Instance
	* Microsoft Windows server 2019 Base
    	* cfg Instance
        	* Network: MyCustomVPC
            * Subnet: PublicSubnet
            * Auto-assign Public IP: Enable
    	* cfg Security group
        	* RDP-IN-Public
            	* Type: RDP
                * Protocole: TCP
                * Port: 3389
                * Source: MyIP

[<img src="https://i.imgur.com/E2puyeD.png">](https://i.imgur.com/E2puyeD.png)
[<img src="https://i.imgur.com/qDrFvQ7.png">](https://i.imgur.com/qDrFvQ7.png)
[<img src="https://i.imgur.com/TwOX0Jp.png">](https://i.imgur.com/TwOX0Jp.png)
[<img src="https://i.imgur.com/n74PP2J.png">](https://i.imgur.com/n74PP2J.png)
[<img src="https://i.imgur.com/nppViUb.png">](https://i.imgur.com/nppViUb.png)
[<img src="https://i.imgur.com/swVUpB9.png">](https://i.imgur.com/swVUpB9.png)
[<img src="https://i.imgur.com/wKBbRBF.png">](https://i.imgur.com/wKBbRBF.png)
[<img src="https://i.imgur.com/94bsCNl.png">](https://i.imgur.com/94bsCNl.png)
[<img src="https://i.imgur.com/37XGH9l.png">](https://i.imgur.com/37XGH9l.png)
[<img src="https://i.imgur.com/Kadmk5T.png">](https://i.imgur.com/Kadmk5T.png)
[<img src="https://i.imgur.com/Os4OjUL.png">](https://i.imgur.com/Os4OjUL.png)

### EC2W19-02
* Launch Instance
	* Microsoft Windows server 2019 Base
    	* cfg Instance
        	* Network: MyCustomVPC
            * Subnet: PrivateSubnet
            * Auto-assign Public IP: Disable
    	* cfg Security group
        	* RDP-IN-Private
            	* Type: RDP
                * Protocole: TCP
                * Port: 3389
                * Source: 10.0.0.0/16
            
[<img src="https://i.imgur.com/QG8iTy7.png">](https://i.imgur.com/QG8iTy7.png)
[<img src="https://i.imgur.com/qBJYNja.png">](https://i.imgur.com/qBJYNja.png)
[<img src="https://i.imgur.com/2PWF3ZB.png">](https://i.imgur.com/2PWF3ZB.png)
[<img src="https://i.imgur.com/CusSS2T.png">](https://i.imgur.com/CusSS2T.png)

## Multiple sessions
* Users: 
	* administrator
	* admin
	
[<img src="https://i.imgur.com/DXBnpyW.png">](https://i.imgur.com/DXBnpyW.png)	

## ICMPv4 (ping) 
# ping 
* Hosts:
	* EC2W19-01
	* EC2W19-02

[<img src="https://pix.toile-libre.org/upload/original/1598899488.png">](https://pix.toile-libre.org/upload/original/1598899488.png)
[<img src="https://i.imgur.com/PgIWVVH.png">](https://i.imgur.com/PgIWVVH.png)
[<img src="https://i.imgur.com/cOKBMhI.png">](https://i.imgur.com/cOKBMhI.png)

	
