# Quiz 07 - VPC

## Questions
1) You have set up an internet gateway in your VPC, but your EC2 instances still don't have access to the internet.

   Which of the following is **NOT** a possible issue?
   * Route Tables are missing entries
   * The security group does not allow network in
   * The NACL does not allow network traffic out
* [Answer](https://i.imgur.com/f6Y0O7n.png)
2) You would like to provide internet access to your instances in private subnets with IPv4, while making sure
   this solution requires the least amount of administration and scales seamlessly. What should you use?
   * NAT Instances with Source / Destination Check flag off
   * NAT Gateway
* [Answer](https://i.imgur.com/DzHw75J.png)
3) Your EC2 instance in a private subnet must access the AWS APIs privately. You must keep all traffic within the AWS network. What do you recommend?
   * NAT Gateway in public subnet + IGW
   * VPC Endpoints
   * Direct Connect
* [Answer](https://i.imgur.com/p9l3zbt.png)
