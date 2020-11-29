# Alternative htaccess with ALB + NACL

## Acronym
* ALB - Application Load Balancer
* NACL - Network Access Control List

## Tology
[<img src="https://i.imgur.com/3KB5nJw.png">](https://i.imgur.com/3KB5nJw.png)

## Steps
### 01 - User data
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

### 02 - ALB

### 03 - NACL

### 04 - Register Domain ext
* Tucows
