# ELB

## Acronym
* ELB - Elastic Load Balancer
* L - Layer
* SAN - Subject Alternate Name
* LB - Load Balancer
* SSL - Secure Sockets Layer
* SNI - Server Name Indication
* CLB - Classic Load Balancer
* Cert - Certificate
* ALB - Application Load Balancer
* NLB - Network Load Balancer

## Type of LB
* AWS has **3 kinds** of managed LBs
1) CLB (v1 - old generation) - 2009
  * HTTP, HTTPS, TCP
2) ALB (v2 - new generation) - 2016
  * HTTP, HTTPS, WebSocket
3) NLB (v2 - new generation) - 2017
  * TCP, TLS (secure TCP) & UDP
* Overall, it's recommended to use the newer / v2 generation LBs as they provide more features
* You can setup **internal (private)** or **external (public)** ELBs

---

## CLB (v1) Listeners
* Health Checks can be HTTP(L7) or TCP(L4) based
* Supports only one SSL cert
  * The SSL cert can have many SAN, but the SSL cert must be changed anytime a SAN is added/edit/removed
  * Better to use ALB with SNI if possible
  * Can use multiple CLB if you want distinct SSL certificates
* TCP => TCP passes all the traffic to the EC2 instance
  * Only way to use 2-way SSL authentication

* SSL:

| Listener                                                  | Internal                                 |
| --------------------------------------------------------- | ---------------------------------------- |
| HTTP (L7)                                                 | HTTP<br>HTTPS (must install cert on EC2) |
| HTTPS (L7)<br>SSL termination<br>Must install cert on CLB | HTTP<br>HTTPS (must install cert on EC2) |
| TCP (L4)                                                  | TCP<br>SSL (must install cert on EC2)    |
| SSL secure TCP (L4)<br>Must install cert on CLB           | TCP<br>SSL (must install cert on EC2)    |

## Diagram
[<img src="https://i.imgur.com/tVdJjn3.png">](https://i.imgur.com/tVdJjn3.png)

---

## 
