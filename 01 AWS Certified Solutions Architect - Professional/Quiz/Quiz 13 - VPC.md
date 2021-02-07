# Quiz 13 - VPC

## Questions
1) You have created a public subnet with a NAT instance in it, on which you have assigned an Elastic IP. Instances in your private subnet are using the instance to access the internet and download software updates from your company public repository. The security team has asked you for which IP addresses to whitelist in order to let the updates go through. What do you recommend, that won't impact your operations while providing you with the best security?
   * A. Whitelist the private subnet associated private CIDR
   * B. Whitelist the private subnet associated public CIDR
   * C. Whitelist the public sunet associated private CIDR
   * D. Whitelist the public subnet associated public CIDR
   * E. Whitelist the EIP of the NAT Instance
2) You would like to create a dashboard to analyze the amount of DENIED traffic on your VPC, once every week. You want to keep the costs at a minimum. What do you suggest?
   * A. Create a VPC Flow Log & send the data to Amazon CloudWatch Logs, create a Log subscription & hook Kinesis Data Firehose to it. Send the data from KDF into S3. Create a QuickSight dashboard backed by Athena
   * B. Create a VPC Flow Logs & send the data to Amazon CloudWatch Logs, create a Log subscription & hook Kinesis Data Firehose to it. Send the data from KDF into S3. Create a QuickSight dashboard backed by Redhisft
   * C. Create a VPC Flow Log & send the data to Amazon S3. Create a QuickSight dashboard backed by Redshift
   * D. Create a VPC Flow Log & send the data to Amazon S3. Create a QuickSight dashboard backed by Athena
3) You are looking to set up a hub and spoke model between your data centers and multiple VPC, with minimal management and the ability to quickly add new VPC in the future. What do you suggest?
   * A. Setup a Direct Connect connection to each VPC. For a new VPC, provision a new DX connection
   * B. Setup VPN connections between the data center & each VPC. Setup static route management
   * C. Setup VPN connections between the data center & each VPC. Setup dynamic BGP route management
   * D. Enable VPC peering between all VPC, & peer the final VPC over via VPN to the data center
4) You would like to privately access Amazon S3 from your on-premise data center. You have set up Direct Connect between on-premise and AWS. What do you suggest?
   * A. Set up a VPC Endpoint Gateway, & use that to access Amazon S3
   * B. Set up a VPC Endpoint interface, & use that to access Amazon S3
   * C. Access Amazon S3 over the private VIF
   * D. Access Amazon S3 over the pbulic VIF
5) EC2 instances deployed in your public subnet are looking to access Amazon S3 buckets privately and so you have set up a VPC Endpoint Gateway. You need to ensure the traffic goes through this VPC Endpoint Gateway only. How should you set up your bucket policy to ensure this type of access?
   * A. Use an AWS:SourceIp condition on the public IP range of your EC2 instances
   * B. Use an AWS:SourceIp condition on the private IP range of your subnet
   * C. Use an AWS:sourceVpce based on the endpoint you have created
   * D. Use an AWS:sourceVpc based on the endpoint you have created
   * E. Use an AWS:sourceIp condition on the private IP range of your VPC Endpoint Gateway
6) Your company has created a REST API that it will sell to hundreds of customers as a SaaS. Your customers are on AWS and are using their own VPC. You would like to allow your customers to access your SaaS without going through the public internet while ensuring your infrastructure is not left exposed to network attacks. What do you recommend?
   * A. Create a VPC Endpoint
   * B. Create a VPC peering connection
   * C. Create a ProvateLink
   * D. Create a Direct Connect
* [Answers](https://i.imgur.com/KEkRHx3.png)
* Score:
  [07-02-2021 PM] - 2/6 = 33.3%
