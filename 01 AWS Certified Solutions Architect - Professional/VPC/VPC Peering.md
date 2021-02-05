# VPC Peering

## Doc
* [One VPC peered with two VPCs using longest prefix match](https://docs.aws.amazon.com/vpc/latest/peering/peering-configurations-partial-access.html#one-to-two-vpcs-lpm)
* [Unsupported VPC peering configurations](https://docs.aws.amazon.com/vpc/latest/peering/invalid-peering-configurations.html)

## Acronym
* CIDR - classless Inter-Domain Routing
* SG - Security Group
* VPC - Virtual Private Cloud

## Intro
* Networking connection between two VPCs
* Works with IPv4 & IPv6
* Multi-account & multi-region
* Traffic stays private on AWS network
* Must not have overlapping CIDR
* VPC Perring connection is **not transitive** (must be established for each VPC that need to communicate with one another)
* You can do VPC peering with another AWS account
* You must update route tables in <ins>each VPC's subnets</ins> to ensure instances can communicate

### Diagram
[<img src="https://i.imgur.com/8q4u152.png">](https://i.imgur.com/8q4u152.png)
[<img src="https://i.imgur.com/uDSjQdE.png">](https://i.imgur.com/uDSjQdE.png)
[<img src="https://i.imgur.com/j56jPDm.png">](https://i.imgur.com/j56jPDm.png)

---

## Good to know
* VPC peering can work **inter-region**, cross-account
* You can reference a SG of a peered VPC (works cross account)
  * e.g

|Type|Protocol|Port Range|Source|
|----|--------|----------|------|
|HTTP|TCP     | 80       |sg-00d2b0f5fd6de757e|
|HTTP|TCP     | 80       |sg-013347765f7a63aae/12356788|

---

## Longest Prefix Match
* VPC uses the longest prefix match to select the most specific route

* Route table:

<html>
<body>
<table cellspacing="0" border="0">
	<colgroup span="3" width="107"></colgroup>
	<tr>
		<td height="21" align="left" valign=bottom><font color="#000000">Route Table</font></td>
		<td align="left" valign=bottom><font color="#000000">Destination</font></td>
		<td align="left" valign=bottom><font color="#000000">Target</font></td>
	</tr>
	<tr>
		<td rowspan=3 height="63" align="center" valign=middle><font color="#000000">VPC A</font></td>
		<td align="left" valign=bottom><font color="#000000">172.16.0.0/16</font></td>
		<td align="left" valign=bottom><font color="#000000">Local</font></td>
	</tr>
	<tr>
		<td align="left" valign=bottom><font color="#000000">10.0.0.77/32</font></td>
		<td align="left" valign=bottom><font color="#000000">pcx-aaaabbbb</font></td>
	</tr>
	<tr>
		<td align="left" valign=bottom><font color="#000000">10.0.0.0/16</font></td>
		<td align="left" valign=bottom><font color="#000000">pcx-aaaacccc</font></td>
	</tr>
	<tr>
		<td rowspan=2 height="42" align="center" valign=middle><font color="#000000">VPC B</font></td>
		<td align="left" valign=bottom><font face="Cambria">10.0.0.0/16</font></td>
		<td align="left" valign=bottom><font color="#000000">Local</font></td>
	</tr>
	<tr>
		<td align="left" valign=bottom><font color="#000000">172.16.0.0/16</font></td>
		<td align="left" valign=bottom><font color="#000000">pcx-aaaabbbb</font></td>
	</tr>
	<tr>
		<td rowspan=2 height="42" align="center" valign=middle><font color="#000000">VPC C</font></td>
		<td align="left" valign=bottom><font color="#000000">10.0.0.0/16</font></td>
		<td align="left" valign=bottom><font color="#000000">Local</font></td>
	</tr>
	<tr>
		<td align="left" valign=bottom><font color="#000000">172.16.0.0/16</font></td>
		<td align="left" valign=bottom><font color="#000000">pcx-aaaacccc</font></td>
	</tr>
</table>
<!-- ************************************************************************** -->
</body>

</html>

* here the longest prefix for 10.0.0.77 is **10.0.0.77/32** (route table VPC A)
* (other way of saying it is "most specific route")

### Diagram
[<img src="https://i.imgur.com/JWN1WGM.png">](https://i.imgur.com/JWN1WGM.png)

---

## Invalid Configurations
* Overlapping CIDR for IPv4
* No Transitive VPC Peering
* No Edge to Edge Routing
  * VPN, Direct Connect, IGW, NAT, Gateway VPC Endpoint (S3 & DynamoDB)

### Diagram
[<img src="https://i.imgur.com/Adwbzsk.png">](https://i.imgur.com/Adwbzsk.png)

[<img src="https://i.imgur.com/dIUSeTS.png">](https://i.imgur.com/dIUSeTS.png)

[<img src="https://i.imgur.com/YwfRU7c.png">](https://i.imgur.com/YwfRU7c.png)

---

## No edge to edge routing (Invalid configuration)
* This is an invalid configuration
* VPC Peering does not support edge to edge routing for NAT devices

### Diagram
[<img src="https://i.imgur.com/2EfnPa6.png">](https://i.imgur.com/2EfnPa6.png)
