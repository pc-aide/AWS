# Global Infrastructure

## Acronym
* CDN - Content Delivery Network

## Doc
* https://aws.amazon.com/about-aws/global-infrastructure/

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
* host a content delivery network, or CDN (CloudFront)
	* CloudFront
    	* To deliver content to your customers
