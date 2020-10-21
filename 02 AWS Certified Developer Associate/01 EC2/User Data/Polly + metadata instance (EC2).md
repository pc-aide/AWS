# Polly + metadata instance (EC2).md

## Prereq
1. IAM Role: PollyAccess
2. AMI : Amazon Linix 2

## bootstrap
````bash
#!/bin/bash

# Install Apache Web Server
yum update -y
yum install httpd -y
systemctl start httpd
systemctl enable httpd

# Discover configuration using the EC2 metadata service
ID=$(curl 169.254.169.254/latest/meta-data/instance-id)
TYPE=$(curl 169.254.169.254/latest/meta-data/instance-type)
AZ=$(curl 169.254.169.254/latest/meta-data/placement/availability-zone)
IPV4=$(curl 169.254.169.254/latest/meta-data/public-ipv4)

# Set up the Web Site
cd /var/www/html

# Make AWS Cloud API calls to generate an audio file
VOICE=$(aws polly describe-voices \
--language-code en-US \
--region ca-central-1 \
--query Voices[0].Id \
--output text)
aws polly synthesize-speech \
--region ca-central-1 \
--voice-id $VOICE \
--text "Hello from EC2 instance $ID." \
--output-format mp3 instance.mp3

# Generate customized index.html for this instance
echo "<html><body><h1>Welcome to your EC2 Instance</h1><p><p>" > ./index.html
echo "<audio controls>" >> ./index.html
echo '<source src="instance.mp3" type="audio/mp3">' >> ./index.html
echo 'Here is an <a href="instance.mp3"> audio greeting.</a>  ' >> ./index.html
echo "</audio><p><p>" >> ./index.html
echo "There ar many other instance, but" >> ./index.html
echo "<strong>$ID</strong> is your. <p><p>" >> ./index.html
echo "This is a <strong>$TYPE</strong> instance" >> ./index.html
echo " in <strong>$AZ</strong>. <p><p>" >> ./index.html
if [ "$IPV4" ];
then
    echo "The public IP is <strong>$IPV4</strong>.<p><p>" >> ./index.html
else
    echo "This instance does <strong>NOT</strong> have" >> ./index.html
    echo "a public iP address.<p><p>" >> ./index.html
fi
echo "--Audio provided by the $VOICE. <p><p>" >> ./index.html
echo "</body></html>" >> ./index.html
````

---

## Test
* Browser:
[<img src="https://i.imgur.com/Pg54nXT.png">](https://i.imgur.com/Pg54nXT.png)
