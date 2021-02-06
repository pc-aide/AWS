# PrivateLink

## Doc
* [How to use AWS PrivateLink to secure & scale web filtering using explicit proxy](https://aws.amazon.com/blogs/networking-and-content-delivery/how-to-use-aws-privatelink-to-secure-and-scale-web-filtering-using-explicit-proxy/)

## Acronym
* AZ - Availability Zone
* ENI - Elastic Network Interface
* NAT - Network Address Translation
* NLB - Network Load Balancer
* VPC - Virtual Private Cloud

## AWS PrivateLink (VPC Endpoint Services)
* Most secure & scalable way to expose a service to thousands of VPC (own or other accounts)
* Doest not require VPC peering, internet gateway, NAT, route tables...
* Requires a network load balancer (Service VPC) and ENI (Customer VPC)
* If the NLB is multiple AZ, and the ENI in multiple AZ, the solution is fault tolerant

### Diagram
[<img src="https://i.imgur.com/Ill9QjG.png">](https://i.imgur.com/Ill9QjG.png)

---

## Secure & Scale Web Filtering using Explicit Proxy
[<img src="https://i.imgur.com/zIu720s.png">](https://i.imgur.com/zIu720s.png)
