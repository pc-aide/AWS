# Global Infrastructure

## Acronym
* CDN - Content Delivery Network

## Doc
* [Global-Infrastructure](https://aws.amazon.com/about-aws/global-infrastructure/)
* [Regions, Availability Zones, and Local Zones](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Concepts.RegionsAndAvailabilityZones.html)

## Topology
1) Regions
	* Host : Availability Zone
    * Optimize latency
    * Minimizing costs
    * Adhering to regulatory requirements (politique IT)
* E.g.
	* dev resources -> 1 region
    * primary customer -> different region
* E.g.02
	* Deploy resource -> multiple regions
    * to provide a consisten experience globally
* S3 or EC2 available in all regions

[<img src="https://i.imgur.com/z3k8JuV.png">](https://i.imgur.com/z3k8JuV.png)

* List
	* US East (N. Virginia) | us-east-1
	* US East (Ohio) | us-east-2
	* US West (N. California) | us-west-1
	* US West (Oregon) | us-west-2
	* Africa (Cape Town) | af-South-1
	* Asia Pacific (Hong Kong) | ap-east-1
	* Asia Pacific (Mumbai) | ap-south-1
	* Asia Pacific (Seoul) | ap-southeast-1
	* Asia Pacific (Singapore) | ap-southeast-2
	* Asia Pacific (Sydney) | ap-northeast-1
	* Canada (Central) | ca-central-1
	* Europe (Frankfurt) | eu-central-1
	* Europe (Ireland) | eu-west-1
	* Europe (London) | eu-west-2
	* Europe (Milan) | eu-south-1
	* Europe (Paris) | eu-west-3
	* Europe (Stockholm) | eu-north-1
	* Middle East (Bahrain) | me-south-1
	* South America (Sao Paulo) | sa-east-1

2) Availability Zones
* Collection of data centers in a specific region
* Each Availability zone is physically isolated
	* connected together by a fast
    * low-latency network
    * provisioning your data across multiple Availability Zones

3) Edge locatlions
* An Edge location is a datacenter owned by a trusted partnet of AWS whci has a **direct connection**
  to the AWS network
* Theses location serve requests for **CloudFront** & **Route 53**. Requests goint ot either of 
  these services will be routed to the nearest edge location automatically.
* **S3 Transfer Acceleration** traffic & **API Gateway** endpoint traffic also use the AWS Edge
  Network.
* This allows for **low latency** no matter where the end user is geographically located
