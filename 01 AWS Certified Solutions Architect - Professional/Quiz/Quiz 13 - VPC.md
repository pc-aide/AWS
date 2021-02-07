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
   * A. Setup a Direct Connect connection to each VPC. 
4)
5)
6)
* [Answers]()
* Score:
  [] - /6 =
