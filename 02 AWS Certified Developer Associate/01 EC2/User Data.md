# User Data
* It is possible to bootstrap our instances using an EC2 user data **script (launch EC2 start)**
* Bootstrapping means lauching commands when a machine starts (one only time or each time for EC2 start)
* EC2 user data is used to **automated boot tasks** :
  * Installing updates
  * Installing softwares
  * Downloading common file from the internet
  * etc

## Linux
* Need run with the root use (sudo rights)
* Script:
````Bash
#!/bin/bash

###############################################
### USE THIS FILE IF LANCHED AMAZON LINUX 2 ###
###############################################

# Priviledges
sudo su

# Hostname
hostnamectl set-hostname EC2Ama-01

# TimeZone
timedatectl set-timezone america/toronto

# Install httpd
yum update -y
yum install -y httpd
systemctl start httpd
systemctl enable httpd
echo "Hello World from $(hostname -f)" > /var/www/html/index.html
````

* Demo
 * User data:
 
[<img src="https://i.imgur.com/hr7ZUFj.png">](https://i.imgur.com/hr7ZUFj.png)
[<img src="https://i.imgur.com/8Bbwm0t.png">](https://i.imgur.com/8Bbwm0t.png)
[<img src="https://i.imgur.com/nO7XV6F.png">](https://i.imgur.com/nO7XV6F.png)

## Windows

### Batch

### PowerShell
