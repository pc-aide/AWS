02 Alternative htaccess with ALB + NACL

## Acronym
* ALB - Application Load Balancer
* SG - Security Group
* VPC - Virtual Private Cloud
* NACL - Network Access Control List
* VPC - Virutal Private Cloud
* LB - Load Balancer

## Resources
1) EC2 
2) New VPC
  1) subnet public
  2) Internet Gateway
  3) Route table
  4) NACL (white IP address)
2) ALB
3) Domain Register ext (tucows)


## Topoligy
[<img src="https://i.imgur.com/Bp1tJTB.png">](https://i.imgur.com/Bp1tJTB.png)


## Steps
### 01 - VPC
* create own VPC
  * then:
    * 2x subnets public -  mandatory for ALB
      * ca-central-1a : 10.10.1.0/24
      * ca-central-1b : 10.10.2.0/24 - we don't use for the demo
    * route table 
    * internet gate way
    * now my VPC (subnet public + route table) done
* Create SG for new VPC
  1) IN-SSH-MyIP
  2) IN-HTTP-Any
  3) IN-HTTP-LB

### 02 - ALB
* Create new onw
  * Name: tucowstestALB

### 03 - EC2
* create new instance with user data + new VPC
  * user data
````bash
#!/bin/bash

# Install httpd
yum update -y
yum install -y httpd
systemctl start httpd
systemctl enable httpd

# Index.html
echo " <html>
  <title>login</title>
  <head>
    <img src="https://i.imgur.com/ua6uZng.png" 
  </head>
  <body>
    <h1>Please Login</h1>
    <!-- Email -->
    <input
     id="login"
     name="login"
     value=""
     type="text"
     class="form-control " 
     placeholder="Email">
    <!-- Password -->
    <input 
      id="password" 
      name="password" 
      type="password" 
      class="form-control " 
      placeholder="Password" 
      value="">
  </body>
</html>" > /var/www/html/index.html

# Reload httpd
systemctl reload httpd
````

### 04 - NACL
* Create new one
  * 1st White IP add
    * 143.244.60.130 - ok
  * 2 nd white list:
    * 
* now we have 2 IPs different for alternative htaccess via NACL
* we can access this app onto ALB with NACL (white list like htaccess)
done
* atlanta don't have acces this web site, just need update NACL for allow or deny
* timeout
