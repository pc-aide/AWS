# Quiz 02 - EC2 Final

## Questions
1) You plan on running an open-source MongoDB database year-round on EC2. Which instance launch mode should you choose?
    * On-Demand
    * Reserved Instances
    * Spot Instances
* [Answer](https://i.imgur.com/fvMr8Pc.png)
2) You are launching an EC2 instance in us-east-1 using this Python script snippet:

   (we will see SDK in a later section, for now just look at the code reference ImageId)
   ````Python
   ec2.create_instance(ImageID='ami-b23a5e7', MinCount=1, MaxCount=1)
   ````
   It works well, so you decide to deploy your script in us-west-1 as well. There, the script does
   not work and fails with "ami not found" error. What's the problem?
    * AMI is region locked & the same ID cannot be used across regions
    * The AMI needs to first be shared to another region. The same ID can then be used
* [Answer](https://i.imgur.com/hJauVRV.png)
3) You would like to deploy a database technology and the vendor license bills you based on the physical
   cores and underlying network socket visibility. Which EC2 launch modes allow you to get visibility into them?
    * Spot Instances
    * Dedicated Hosts
    * On-Demand
* [Answer](https://i.imgur.com/i4u10I7.png)
4) You are running a critical workload of three hours per week, on Monday. As a solutions architect, which EC2 Instance
   Launch Type should you choose to maximize the cost savings while ensuring the application stability?
    * On-Demand Instances
    * Reserved Instances
    * Spot Instances
    * Scheduled Reserved Instances
* [Answer](https://i.imgur.com/JMM3JR3.png)
