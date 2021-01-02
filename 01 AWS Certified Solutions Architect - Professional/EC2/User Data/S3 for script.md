# S3 for script

## Intro
* user data
````sh
#!/bin/bash
aws s3 cp <bucket/web-server.sh>
/home/ec2-user/web-server.sh
chmod +x /home/ec2-user/web-server.sh
/home/ec2-user/web-server.sh
````
* dont' forget IAM role!
