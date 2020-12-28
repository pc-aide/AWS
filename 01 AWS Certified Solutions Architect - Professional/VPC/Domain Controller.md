# Domain Controller

## Acronym
* dc - Domain Controller
* SG - Security Group

## Diagram
[<img src="https://i.imgur.com/bfVpXXd.png">](https://i.imgur.com/bfVpXXd.png)

---

## DomainControllerSG

* Inbound Rule (demo)


| Type            | Protocol | Port Range  | Source               |
|-----------------|----------|-------------|----------------------|
| Custom UDP Rule | UDP      | 49152-65535 | sg-06b6a789fa17578ef |
| Custom UDP Rule | UDP      | 464         | sg-06b6a789fa17578ef |
| Custom TCP Rule | TCP      | 49152-65535 | sg-06b6a789fa17578ef |
| Custom UDP Rule | UDP      | 389         | sg-06b6a789fa17578ef |
| DNS (UDP)       | UDP      | 53          | 10.0.0.0/16          |
| SMB             | TCP      | 445         | sg-06b6a789fa17578ef |
| ALL ICMP - IPv4 | All      | N/A         | sg-06b6a789fa17578ef |
| WinRM-HTTP      | TCP      | 5985        | 10.0.0.0/16          |
| All traffic     | All      | All         | sg-09c698b6cfac9519d |
| Custom TCP Rule | TCP      | 139         | sg-06b6a789fa17578ef |
| Custom TCP Rule | TCP      | 135         | sg-06b6a789fa17578ef |


---

## DomainMembersSG
* Replication DC

* Inbound Rule (demo)

| Type            | Protocol | Port Range  | Source               |
|-----------------|----------|-------------|----------------------|
| Custom UDP Rule | UDP      | 445         | sg-09c698b6cfac9519d |
| Custom UDP Rule | UDP      | 49152-65535 | sg-09c698b6cfac9519d |
| Custom TCP Rule | TCP      | 49152-65535 | sg-09c698b6cfac9519d |
| Custom TCP Rule | TCP      | 636         | sg-09c698b6cfac9519d |
| Custom UDP Rule | UDP      | 389         | sg-09c698b6cfac9519d |
| LDAP            | TCP      | 389         | sg-09c698b6cfac9519d |
| SMB             | TCP      | 445         | sg-09c698b6cfac9519d |
| Custom UDP Rule | UDP      | 88          | sg-09c698b6cfac9519d |
| Custom TCP Rule | TCP      | 88          | sg-09c698b6cfac9519d |
