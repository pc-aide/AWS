# 00 Install

## Acronym
* AMI - Amazon Machine Image

## AMI
* Ubuntu Server 1804.5 LTS
  * awscli not installed

## Doc
* https://docs.aws.amazon.com/cli/latest/userguide/aws-cli.pdf

## search
````Bash
apt get search --name-only ^awscli
````
[<img src="https://i.imgur.com/wgLSQsJ.png">](https://i.imgur.com/wgLSQsJ.png)

## Install
### Version 1
````Bash
# -y : yes to install (no prompt)
apt install -y awscli
````
````Bash
aws --version
````
[<img src="https://i.imgur.com/2ywexVo.png">](https://i.imgur.com/2ywexVo.png)

**We recommended to use the version 2 (more features)**

### Version 2
````Bash
wget "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip
````
[<img src="https://i.imgur.com/9QVhp2q.png">](https://i.imgur.com/9QVhp2q.png)

```Bash
unzip awscli-exe-linux-x86_64.zip; cd aws/ ; ls
```
[<img src="https://i.imgur.com/rblYsLv.png">](https://i.imgur.com/rblYsLv.png)

````Bash
./install ; aws --version
````
[<img src="https://i.imgur.com/oQdp0at.png">](https://i.imgur.com/oQdp0at.png)


## help
````Bash
aws help
````
[<img src="https://i.imgur.com/qAraxTA.png">](https://i.imgur.com/qAraxTA.png)
