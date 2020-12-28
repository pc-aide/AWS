# NACLs

## Acronym
* NACL - Network Access Controller List\
* VPC - Virtual Private Cloud

## Intro
* Traditional access control list
* Inbound & outbound traffic
* Composed of **numbered** rules
  * they're evaluated in the order of the numbers
* Allow or deny action
* Stateless traffic evaluation
  * they're not aware of a session that's been established between two endpoints
    * you have to make sure you're not only allowing the outbound traffic but also allowing the inboud response traffic which could be on an ephemeral port
* **Associated with subnets**
* Default NACL in VPC

---

## NACL Association
* Default NACL for non-associated subnets
* Catch all deny rule
* One NACL per subnet
* Rule evaluation is in order of rules (smallest to biggest)

---

## Diagram
[<img src="https://i.imgur.com/pC4Jhcq.png">](https://i.imgur.com/pC4Jhcq.png)
