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
yum -y
````

### Windows
