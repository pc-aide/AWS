# EC2 User Data

## Intro
* It is possible to bootstrap our instance using an **EC2 User data** script
* **bootstrapping** means lauching commands when a machine starts
* That script is **only run once** at the instance **first start** & never run again
* EC2 user data is used to automate boot tasks such as:
  * Installing updates
  * Installing software
  * Downloading common files from the internet
  * Anthing you can think of
* Linux
  * The EC2 User Data Script runs with the root user
* Windows
  * pending ...

## Examples
### Linux
* Bootstrapping :
````bash
#!/bin/bash

#################################################
## USE THIS FILE IF YOU LAUCHED AMAZON LINUX 2 ##
#################################################

#Get admin priviledges
sudo -s

# Install httpd (Linux 2 version)
yum update -y
yum install -y httpd
systemctl start httpd
systemctl enable httpd
echo "Hello World from $(hostname -f)" > /var/www/html/index.html
````

* AWS Console new instalnce launch:

[<img src="https://i.imgur.com/BCLtgNC.png">](https://i.imgur.com/BCLtgNC.png)

* pending ... :

[<img src="https://i.imgur.com/eaUhSp1.png">](https://i.imgur.com/eaUhSp1.png)

* Test 
 * same thing without do do again for new EC2
 
[<img src="https://i.imgur.com/MOIZ1QV.png">](https://i.imgur.com/MOIZ1QV.png)

### Windows
