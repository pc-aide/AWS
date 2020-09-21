# User Data
* It is possible to bootstrap our instances using an EC2 user data **script (launch EC2 start)**
* Bootstrapping means lauching commands when a machine starts (one only time or each time for EC2 start)
* EC2 user data is used to **automated boot tasks** :
  * Installing updates
  * Installing softwares
  * Downloading common file from the internet
  * etc

## Doc
* [Windows](https://docs.aws.amazon.com/AWSEC2/latest/WindowsGuide/ec2-windows-user-data.html)
* [Linux](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/user-data.html)

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
timedatectl set-timezone America/Toronto

# Install httpd
yum update -y
yum install -y httpd
systemctl start httpd
systemctl enable httpd
echo "Hostname: <p style=color:red>$(hostname -f)</p>" > /var/www/html/index.html
# Which AZ for EC2
EC2_AZ=$(curl -s http://169.254.169.254/latest/meta-data/placement/availability-zone)
echo "<p>In AZ:</p>" >> /var/www/html/index.html
echo "<p style=color:green>In $EC2_AZ</p>" >> /var/www/html/index.html

# Reload httpd
systemctl reload httpd
````

* Demo
 * User data:
 
[<img src="https://i.imgur.com/hr7ZUFj.png">](https://i.imgur.com/hr7ZUFj.png)
[<img src="https://i.imgur.com/8Bbwm0t.png">](https://i.imgur.com/8Bbwm0t.png)
[<img src="https://i.imgur.com/nO7XV6F.png">](https://i.imgur.com/nO7XV6F.png)

## Windows
* On Windows we are using tag (like html)
* Don't need specific administrator (run as admin), just put your code into tag
* For batch: <script> your code here</script>
* For PowerShell: <PowerShell>...codes...</PowerShell>

### Batch

### PowerShell
