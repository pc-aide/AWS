# WorkSpaces

## Acronym
* AD - Active Directory
* VDI - Virtual Desktop Infrastructure
* WAM - WorkSpaces Application Manager

## Intro
* Managed, Secure Cloud Desktop
* Great to eliminate management of on-premise VDI 
* On Demand, pay per by usage
* Secure, Encrypted, Network Isolation
* Integrated with Microsoft AD
* WAM
  * Deploy & Manage applications as virtualized application containers
  * Provision at scale, & keep the applications updated using WAM
* Windows Updates  
  * By default, Amazon Workspaces are configured to install software updates
  * Amazon WorkSpaces with Windows will have Windows Update turned on
  * You have full control over the Windows Update frequency
* Maintenance Windows
  * Updates are installed during maintenance windows (you define them)
  * Always On WorkSpaces: default is from 00h00 t0 04h00 on Sunday morning
  * AutoStop WorkSpaces: automatically starts once a month to install updates
  * Manual maintenance: you define your windows & perform maintenance

### Diagram
[<img src="https://i.imgur.com/B5mLz3i.png">](https://i.imgur.com/B5mLz3i.png)
