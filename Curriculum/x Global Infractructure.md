# AWS Global Infrastructure

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
	* deploy resource -> multiple regions
    * to provide a consisten experience globally
* S3 or EC2 available in all regions
* Doc : https://aws.amazon.com/about-aws/global-infrastructure/

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
