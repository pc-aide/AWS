# Gateway Endpoints

## Acronym
* SG - Security Group
* NACL - Network Access Control List
* VPC - Virtual Private Cloud

## Gateway VPC Endpoints
1) Select the service & VPC using prefix list
2) Attach an endpoint policy to the endpoint
3) Specify route tables where routes should be created
* One service per endpoint
  * e.g: cant' have DynamoDB & RDS on same endpoint, we need two endpoint here for our 2 services
* One policy per endpoint
* One route per service
* Multiple endpoints per VPC
* Multiple endpints per service

---

## Limitations
* Prefix list only works with SGs, not NACLs
* Endpoints support IPv4 & same region only
* Endpoints can't be extended outside of VPC
* DNS resolutin must be enabled or configured properly   

---

## Diagram
[<img src="https://i.imgur.com/xslKbfi.png">](https://i.imgur.com/xslKbfi.png)
