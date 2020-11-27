# Hostname + AZ.md

## User data
````bash
#!/bin/bash

# Hostname
hostnamectl set-hostname EC2Ama-01

# TimeZone
timedatectl set-timezone America/Toronto

# Install httpd
yum update -y
yum install -y httpd
systemctl start httpd
systemctl enable httpd

# Index.html
echo "<h1>This is a test</h1>" > /var/www/html/index.html
echo "Hostname: " >> /var/www/html/index.html
echo "<p style=color:red>$(hostname -f)</p>" >> /var/www/html/index.html

# Which AZ for EC2
EC2_AZ=$(curl -s http://169.254.169.254/latest/meta-data/placement/availability-zone)
echo "<p>In AZ:</p>" >> /var/www/html/index.html
echo "<p style=color:green>In $EC2_AZ</p>" >> /var/www/html/index.html

# Reload httpd
systemctl reload httpd
````

## Browser
[<img src="https://i.imgur.com/mgTPaLD.png">](https://i.imgur.com/mgTPaLD.png)
