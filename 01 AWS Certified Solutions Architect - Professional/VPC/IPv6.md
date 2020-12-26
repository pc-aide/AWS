# IPv6

## Acronym
* CIDR - Classless Inter-Domain Routing
* EIP - Elastic IP
* VPC - Virtual Private Cloud
* NAT - Network Address Translation 
* S2S - Site to Site
* CG - Customer Gateway

## INtro
* Dual-stack with IPv4
* Limited to number of IPv4 addresses
* CIDR provided by you or AWS
* Global unicast address /56 per VPC
* Each subnet receives a /64
* /56 is 4.7 * 10<sup>21</sup> addresses

---

## IPv6 Assignment
* No public/private addresses
  * we can all addresses like "public" but can't not means reachable (restriction)
* DHCPv6 required on instance
* Manual or automatic assignment
* No AWS provided DNS hostnames
* No EIPv6 addresses
* Not for S2S VPN, CG, NAT & VPC Endpoints
