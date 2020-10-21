# §02 - Intro to Compute & Networking

## Questions
1. When you launch an Amazon Elastic Compute Cloud (Amazon EC2) instance, which of the
following is the most specific type of AWS entity in which you can place it?
    * A. Region
    * B. AZ
    * C. Edge location
    * D. Data center
2. You have saved SSH connection information for an Amazon Elastic Compute Cloud (Amazon
EC2) instance that you launched in a public subnet. You previously stopped the instance the
last time you used it. Now that you have started the instance, you are unable to connect to
the instance using the saved information. Which of the following could be the cause?
    * A. Your SSH key pair has automatically expired
    * B. The public IP of the instance has changed
    * C. The security group rules have expired
    * D. SSH is enabled only for the first boot of an Amazon EC2 instance
3. You are working from a new location today. You are unable to initiate a Remote Desktop
Protocol (RDP) to your Windows instance, which is located in a public subnet. What could
be the cause?
    * A. Your new IP address may not match the inbound security group rules.
    * B. Your new IP address may not match the outbound security group rules.
    * C. RDP is not available for Windows instances, only SSH
    * D. RDP is enabled only for the first 24 hours of your instance runtime
4. You have a backend Amazon EC2 instance providing a web service to your web server
instances. Your web servers are in a public subnet. You would like to block inbound
requests from the internet to your backend instance but still allow the instance to make
API requests over the public internet. What steps must you take? (**Select TWO**.)
    * A. Launch the instance in a private subnet and rely on a NAT gateway in a public subnet
to forward outbound internet requests
    * B. Configure the security group for the instance to explicitly deny inbound requests from
the internet.
    * C. Configure the network access control list (network ACL) for the public subnet to
explicitly deny inbound web requests from the internet.
    * D. Modify the inbound security group rules for the instance to allow only inbound
requests from your web servers
5. You have launched an Amazon Elastic Compute Cloud (Amazon EC2) instance and loaded
your application code on it. You have now discovered that the instance is missing applications on which your code depends. How can you resolve this issue?
    * A. Modify the instance profile to include the software dependencies.
    * B. Create an AWS Identity and Access Management (IAM) user, and sign in to the
instance to install the dependencies
    * C. Sign in to the instance as the default user, and install any additional dependencies that
you need.
    * D. File an AWS Support ticket, and request to install the software on your instance.
6. How can code running on an Amazon Elastic Compute Cloud (Amazon EC2) instance
automatically discover its public IP address?
    * A. The public IP address is presented to the OS on the instance automatically. No extra
steps are required
    * B. The instance can query another Amazon EC2 instance in the same Amazon Virtual
Private Cloud (Amazon VPC).
    * C. You must use a third-party service to look up the public IP.
    * D. The instance can make an HTTP query to the Amazon EC2 metadata service at
169.254.169.254.
7. How can you customize the software of your Amazon Elastic Compute Cloud (Amazon
EC2) instance beyond what the Amazon Machine Image (AMI) provides?
    * A. Provide a user data attribute at launch that contains a script or directives to install
additional packages
    * B. Additional packages are installed automatically by placing them in a special Amazon
Simple Storage Service (Amazon S3) bucket in your account.
    * C. You do not have permissions to install new software on Amazon EC2 aside from what
is in the AMI.
    * D. Unlock the instance using the AWS Key Management Service (AWS KMS) and then
sign in to install new packages.
8. You have a process running on an Amazon Elastic Compute Cloud (Amazon EC2) instance
that exceeds the 2 GB of RAM allocated to the instance. This is causing the process to run
slowly. How can you resolve the issue?
    * A. Stop the instance, change the instance type to one with more RAM, and then start the
instance
    * B. Modify the RAM allocation for the instance while it is running.
    * C. Take a snapshot of the data and then launch a new instance. You cannot change the
RAM allocation.
    * D. Send an email to AWS Support to install additional RAM on the server
9. You have launched an Amazon Elastic Compute Cloud (Amazon EC2) Windows instance,
and you would like to connect to it using the Remote Desktop Protocol. The instance is in
a public subnet and has a public IP address. How do you find the password to the Adminis-
trator account?
    * A. Decrypt the password by using the private key from the Amazon EC2 key pair that you
used to launch the instance.
    * B. Use the password that you provided when you launched the instance
    * C. Create a new AWS Identity and Access Management (IAM) role, and use the password
for that role.
    * D. Create an IAM user, and use the password for that user.
10. What steps must you take to ensure that an Amazon EC2 instance can receive web requests
from customers on the internet? (**Select THREE**.)
    * A. Assign a public IP address to the instance.
    * B. Launch the instance in a subnet where the route table routes internet-bound traffic to
an internet gateway.
    * C. Launch the instance in a subnet where the route table rules send internet-bound traffic
to a NAT gateway.
    * D. Set the outbound rules for the security group to allow HTTP and HTTPS traffic.
    * E. Set the inbound rules for the security group to allow HTTP and HTTPS traffic.
11. Which of the following are true about Amazon Machine Images (AMI)? (**Select TWO**.)
    * A. AMI can be used to launch one or multiple Amazon EC2 instances.
    * B. AMI is automatically available in all AWS Regions.
    * C. All AMIs are created and maintained by AWS.
    * D. AMIs are available for both Windows and Linux instances.
12. Which of the following are true about Amazon Elastic Compute Cloud (Amazon EC2)
instance types? (**Select TWO**.)
    * A. All Amazon EC2 instance types include instance store for ephemeral storage.
    * B. All Amazon EC2 instance types can use EBS volumes for persistent storage.
    * C. Amazon EC2 instances cannot be resized once launched.
    * D. Some Amazon EC2 instances may have access to GPUs or other hardware
accelerators.
13. Which of the following actions are valid based on the Amazon Elastic Compute Cloud
(Amazon EC2) instance lifecycle? (**Select TWO**.)
    * A. Starting a previously terminated instance
    * B. Starting a previously stopped instance
    * C. Rebooting a stopped instance
    * D. Stopping a running instance
14. You have a development Amazon Elastic Compute Cloud (Amazon EC2) instance where
you have installed Apache Web Server and MySQL. How do you verify that the web server
application can communicate with the database given that they are both running on the
same instance?
    * A. Modify the security group for the instance.
    * B. Assign the instance a public IP address.
    * C. Modify the network access control list (network ACL) for the instance.
    * D. No extra configuration is required.
15. What type of route must exist in the associated route table for a subnet to be a public subnet?
    * A. A route to a VPN gateway
    * B. Only the local route is required.
    * C. A route to an internet gateway
    * D. A route to a NAT gateway or NAT instance
    * E. A route to an Amazon VPC endpoint
16. What type of route must exist in the associated route table for a subnet to be a private subnet that allows outbound internet access?
    * A. A route to a VPN gateway
    * B. Only the local route is required.
    * C. A route to an internet gateway
    * D. A route to a NAT gateway or NAT instance
    * E. A route to an Amazon Virtual Private Cloud (Amazon VPC) endpoint
17. Which feature of Amazon Virtual Private Cloud (Amazon VPC) enables you to see which
network requests are being accepted or rejected in your Amazon VPC?
    * A. Internet gateway
    * B. NAT gateway
    * C. Route table
    * D. Amazon VPC Flow Log
18. Which AWS service enables you to track the CPU utilization of an Amazon Elastic
Compute Cloud (Amazon EC2) instance?
    * A. AWS Config
    * B. AWS Lambda
    * C. Amazon CloudWatch
    * D. Amazon Virtual Private Cloud (Amazon VPC)
19. What happens to the data stored on an Amazon Elastic Block Store (Amazon EBS) volume
when you stop an Amazon Elastic Compute Cloud (Amazon EC2) instance?
    * A. The data is moved to Amazon Simple Storage Service (Amazon S3).
    * B. The data persists in the EBS volume.
    * C. The volume is deleted
    * D. An EBS-backed instance cannot be stopped.
20. Which programming language can you use to write the code that runs on an Amazon EC2
instance?
    * A. C++
    * B. Java
    * C. Ruby
    * D. JavaScript
    * E. Python
    * F. All of the above
21. You have launched an Amazon EC2 instance in a public subnet. The instance has a public
IP address, and you have confirmed that the Apache web server is running. However, your
internet users are unable to make web requests to the instance. How can you resolve the
issue? (**Select TWO**.)
    * A. Modify the security group to allow outbound traffic on port 80 to anywhere
    * B. Modify the security group for the web server to allow inbound traffic port 80 from
anywhere.
    * C. Modify the security group for the web server to allow inbound traffic on port 443
from anywhere.
    * D. Modify the security group to allow outbound traffic from port 443 to anywhere.
22. Which of the following are the customer’s responsibility concerning Amazon EC2
instances? (**Select TWO**.)
    * A. Decommissioning storage hardware
    * B. Patching the guest operating system
    * C. Securing physical access to the host machine
    * D. Managing the sign-in accounts and credentials on the guest operating system
    * E. Maintaining the software that runs on the underlying host machine
* [Answers](https://i.imgur.com/OkKZvvk.png)
* Score: 19/22 ≈ 86%
