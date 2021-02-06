# Direct Connect

## Doc
* [What is AWS Direct Connect?](https://docs.aws.amazon.com/directconnect/latest/UserGuide/Welcome.html)
* [Link aggregation groups](https://docs.aws.amazon.com/directconnect/latest/UserGuide/lags.html)
* [Direct Connect gateways](https://docs.aws.amazon.com/directconnect/latest/UserGuide/direct-connect-gateways-intro.html)

## Acronym
* ALB - Application Load Balancer
* DX - Direct Connect
* ISP - Internet Service Provider
* LAG - Link Aggregation Groups
* VIF - Virtual InterFaces
* VPC - Virtual Private Cloud
* VPN - Virtual Private Network


## Intro
* Provides a dedicated <ins>private</ins> connection from a remote network to your VPC
* Dedicated connection must be setup between your DC & AWS Direct Connect locations
* More expensive than running a VPN solution
* Private access to AWS services through VIF
* Bypass ISP, reduce network cost, increase badwidth & stability
* Not redundant by default (must setup a failover DX or VPN)

---

## VIF
* **Public VIF**: Connect to Public AWS Endpoints (S3 buckets, EC2 service, anything AWS...)
* **Private VIF**: To connect to resources in your VPC (EC2 instances, ALB, etc...)
* **Transit Virtual Interface**: To connect to resources in a VPC using a Transit Gateway
* <ins>VPC endpoints can't be accessed through Private VIF (you don't need them)</in>

### Diagram
[<img src="https://i.imgur.com/6JtNlwA.png">](https://i.imgur.com/6JtNlwA.png)

---

## Connection Types
* **Dedicated Connections**: 1Gbps & 10Gbps capacity
  * Physical ethernet port dedicated to a customer
  * Request made to AWS first, then completed by aWS Direct Connect Partners
* **Hosted Connections**: 50Mbps, 500Mbps, to 10Gbps
  * Connection requests are made iva AWS Direct Connect Partners
  * Capacity can be **added or removed on demand**
  * 1,2,4,10Gbps available at select AWS Direct Connect Partners
* Lead times are often longer than 1 month to establish a new connection

---

## Encryption
* Data in transit is <ins>not encrypted</ins> but is private
* AWS Direct Connect + VPN provides an IPsec-encrypted private connection
* Good for an extra level of security, but slightly more complex to put in place

### Diagram
[<img src="https://i.imgur.com/BQHQ339.png">](https://i.imgur.com/BQHQ339.png)

---

## LAG
* Get **Increased speed** & **failover** by summing up existing Direct Connect connections into a **logical one**
* Can aggregate up to 4 (active active mode)
* Can add connections over time to the LAG
* All connections in the LAG must have the same bandwidth
* All connections in the LAG must terminate at the same AWS Direct Connect Endpoint
* Can set a minimum number of connections for the LaG to function

### Diagram
[<img src="https://i.imgur.com/8UkaASw.png">](https://i.imgur.com/8UkaASw.png)

---

## Gateways
* If you want to setup a Direct Connect to one or more VPC in many different regions (same account, cross account), you must use a Direct Connect Gateway

### Diagram
[<img src="https://i.imgur.com/C6iOLll.png">](https://i.imgur.com/C6iOLll.png)
