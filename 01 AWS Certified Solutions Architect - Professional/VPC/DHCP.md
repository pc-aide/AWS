# DHCP

## Acronym
* ntp - network time protocol

## DHCP
* Primary addresses assigned by AWS
* DHCP Options Set
  * domain-name-servers <- IP address of up to four DNS servers
  * domain-name <- Custom domain name to use: e.g. Globomantics.xyz
  * ntp-servers <- IP address of up to four time servers
  * netbios-name-servers <- IP address of up to four NetBIOS name servers
  * netbios-node-type <- NetBIOS node type integer
* Can't bring your own DHCP
