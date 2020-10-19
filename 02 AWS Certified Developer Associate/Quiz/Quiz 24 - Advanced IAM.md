# Quiz 24 - Advanced IAM

## Questions
1. We need to gain access to a Role in another AWS account. How is it done?
    * We should ask for them to create a user for us
    * We should ask for tehm to send us access keys
    * We should use the STS service to gain tempory credentials
* [Answer](https://i.imgur.com/Djx60zc.png)
2. An EC2 instance has an IAM instance role attached to it, providing it read and write access to the S3 bucket "my_bucket". You have tested the IAM instance role and both reads and writes are working. You then remove the IAM role from the EC2 instance and test both read and write again. Writes stopped working but Reads are still working. What is the likely cause of this behavior?
    * The EC2 Instance is using cached temporary IAM credentials
    * Removing an instance role from an EC2 instance ca ntake a few minutes before being active
    * The S3 bucket policy authorizes reads
    * When a read is done on a bucket, there's a grace period of 5 minutes to do the same read again
* [Answer](https://i.imgur.com/Z99pwbo.png)
3. What's this IAM policy allowing you to do?
````json
    {
        "Version": "2012-10-17",
        "Id": "Secret Policy",
        "Statement": [
            {
                "Sid": "EC2",
                "Effect": "Allow",
                "Action": "ec2:*",
                "Resource": "*"
            },
            {
                "Sid": "Passrole",
                "Effect": "Allow",
                "Action": [
                    "iam:PassRole"
                ],
                "Resource": "arn:aws:iam:::role/RDS-*"
            }
        ]
    }
````
    * Allowing you to give any role to RDS instance
    * Allowing you to give any role to EC2 instances
    * Allowing you to give RDS full access to EC2 instances
    * Allowing you to assign IAM Roles to EC2 if they start with "RDS-"
* [Answer](https://i.imgur.com/nKqBvuR.png)
4. Your AWS account is now growing to 200 users and you would like to provide each of these users a personal space in the S3 bucket "my_company_space" with the prefix /home/<username>, where they have read/write access. How can you do this efficiently?
    * Create an S3 bucket policy & change it as users are added & removed
    * Create inline policies for each user as they on-boarded
    * Create one customer-managed policy per user & attach them to the relevant users
    * Create one customer-managed policy with dynamic variables & attach it to a group of all users
* [Answer](https://i.imgur.com/lnQZLJP.png)
