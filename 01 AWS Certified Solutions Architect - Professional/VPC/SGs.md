# SGs

## Acronym
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
