# ALB-SG

## Acronym
* ALB - Application Load Balancer
* SG - Security Group

## Globomantics Web App
* no communication between web-1 & web2
* web-2 need communication between app-1 or app-2 (e.g. app -> MySQL)

[<img src="https://i.imgur.com/urHBPt0.png">](https://i.imgur.com/urHBPt0.png)
[<img src="https://i.imgur.com/WlH3d5s.png">](https://i.imgur.com/WlH3d5s.png)

### Web App Groups
<table cellspacing="0" border="0">
	<colgroup span="5" width="107"></colgroup>
	<tr>
		<td rowspan=6 height="126" align="center" valign=middle><font color="#000000">alb-sg</font></td>
		<td colspan=4 align="left" valign=bottom><font color="#000000">Inbound</font></td>
		</tr>
	<tr>
		<td align="left" valign=bottom><b><font face="Cambria">Type</font></b></td>
		<td align="left" valign=bottom><b><font face="Cambria">Protocol</font></b></td>
		<td align="left" valign=bottom><b><font face="Cambria">Port Range</font></b></td>
		<td align="left" valign=bottom><b><font face="Cambria">Source</font></b></td>
	</tr>
	<tr>
		<td align="left" valign=bottom><font color="#000000">HTTP</font></td>
		<td align="left" valign=bottom><font face="Cambria">TCP</font></td>
		<td align="right" valign=bottom sdval="80" sdnum="1033;"><font color="#000000">80</font></td>
		<td align="left" valign=bottom><font color="#000000">0.0.0.0/0</font></td>
	</tr>
	<tr>
		<td colspan=4 align="left" valign=bottom><font color="#000000">Outbound</font></td>
		</tr>
	<tr>
		<td align="left" valign=bottom><b><font color="#000000">Type</font></b></td>
		<td align="left" valign=bottom><b><font color="#000000">Protocol</font></b></td>
		<td align="left" valign=bottom><b><font color="#000000">Port Range</font></b></td>
		<td align="left" valign=bottom><b><font color="#000000">Source</font></b></td>
	</tr>
	<tr>
		<td align="left" valign=bottom><font color="#000000">All traffic</font></td>
		<td align="left" valign=bottom><font color="#000000">All</font></td>
		<td align="left" valign=bottom><font color="#000000">All</font></td>
		<td align="left" valign=bottom><font face="Cambria">0.0.0.0/0</font></td>
	</tr>
	<tr>
		<td rowspan=6 height="126" align="center" valign=middle><font color="#000000">web-sg</font></td>
		<td colspan=4 align="left" valign=bottom><font color="#000000">Inbound</font></td>
		</tr>
	<tr>
		<td align="left" valign=bottom><b><font color="#000000">Type</font></b></td>
		<td align="left" valign=bottom><b><font color="#000000">Protocol</font></b></td>
		<td align="left" valign=bottom><b><font color="#000000">Port Range</font></b></td>
		<td align="left" valign=bottom><b><font color="#000000">Source</font></b></td>
	</tr>
	<tr>
		<td align="left" valign=bottom><font color="#000000">HTTP</font></td>
		<td align="left" valign=bottom><font color="#000000">TCP</font></td>
		<td align="right" valign=bottom sdval="80" sdnum="1033;"><font color="#000000">80</font></td>
		<td align="left" valign=bottom><font color="#000000">alb-sg</font></td>
	</tr>
	<tr>
		<td colspan=4 align="left" valign=bottom><font color="#000000">Outbound</font></td>
		</tr>
	<tr>
		<td align="left" valign=bottom><b><font color="#000000">Type</font></b></td>
		<td align="left" valign=bottom><b><font color="#000000">Protocol</font></b></td>
		<td align="left" valign=bottom><b><font color="#000000">Port Range</font></b></td>
		<td align="left" valign=bottom><b><font color="#000000">Source</font></b></td>
	</tr>
	<tr>
		<td align="left" valign=bottom><font color="#000000">All traffic</font></td>
		<td align="left" valign=bottom><font color="#000000">All</font></td>
		<td align="left" valign=bottom><font color="#000000">All</font></td>
		<td align="left" valign=bottom><font color="#000000">0.0.0.0/0</font></td>
	</tr>
</table>

