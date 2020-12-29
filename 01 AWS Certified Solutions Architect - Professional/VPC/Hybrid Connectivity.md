# Hybrid Connectivity

## Acronym
* AZ - Availability Zone
* ENI - Elastic Network Interface

## Connectivity Options
1) Virtual private gateway for site-to-side VPN
2) EC2 instances for site-to-site VPN
3) Direct Connect
4) Transit VPC
5) Transit gateway

---

## Site-to-site VPN Options
* Two options:
  1) Virtual private gateway
    * Managed by AWS
    * One per VPC
    * Multiple AZs
    * Connects to customer gateway
    * Two tunnels per connection
    * Static or dynamic routing
    * Restricted to resources with an ENI
    * No scaling option
  2) EC2 instance
    * Managed by you
    * Multiple per VPC
    * Single AZ
    * Connection is software dependent
    * Multiple tunnels requires load balancing
    * Scripted route table changes
    * Access to anything with a Private IP
    * Scalable with load balancing
