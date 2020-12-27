# SGs

## Acronym
* CIDR - Classless Inter-Domain Routing
* SG - Security Group
* VPC - Virtual Private Cloud

## Intro
* Virtual firewall at level the instance EC2
* Inbound & outbound traffic
* Composed of rules
* **Allow only**, implicit deny
* Stateful traffic inspection
* Associated with network interface
* Default SG in VPC

---

## SG Association
* Default SG for non-associated instances
* No implicit allow between group members
* Single interface can be a member of multiple groups
* Rule evaluation is additive

---

## SG default
* Inbound rules
  * All traffic allow (all protocol & all port range)
* Outbound rule
  * idem
* We can edit this SG default for different something 

---

## Inbound or Outbound
* Protocol
  * TCP, UDP, ICMP (ping), or custom
* Port range
  * from 0 to 65 535
  * from 0 t0 1023 well-know ports
    * e.g:
      * 80 -> http
      * 22 -> ssh
      * 21 -> ftp
      * 443 -> https
      * 53 -> DNS
      * 3389 -> rdp
* Source (Inbound)
  * CIDR, IP, SG
* Destination (Outbound)
  * CIDR, IP, SG, **prefix list (pl)**
