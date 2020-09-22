# VPC, Subnets, IGW & NAT

## Doc

## Acronym
* VPC - Virtual Private Cloud
* IGW - Internet Gateway
* NAT - Network address translation
* AZ - Availability Zone
* CIDR - Classless inter-domain routing

## VPC & Subnets Primer
* **VPC**: private network to deploy your resource (**regional** resource)
* **Subnets**: allow you to partition your network inside your VPC (AZ resource)
* A **public subnet** is a subnet that is accessible from the internet
* A **private subnet** is a subnet that is not accessible from the internet
* To define access to the internt & between subnets, we use **Route Tables**

### Topology
[<img src="https://i.imgur.com/jaWcfyF.png">](https://i.imgur.com/jaWcfyF.png)

---

## VPC Diagram
[<img src="https://i.imgur.com/JRvA7qf.png">](https://i.imgur.com/JRvA7qf.png)

---

## IGW & NAT gateways
* **Internet Gaeways** helps our VPC instances connect with the internet
* Public Subnets have a route to the IGW
* **NAT Gateways** (AWS-managed) & **NAT Instances** (self-managed) allow your instances in your **Private Subnets** to access the internet while remaining private

### Topology
[<img src="https://i.imgur.com/jjgmmzP.png">](https://i.imgur.com/jjgmmzP.png)
