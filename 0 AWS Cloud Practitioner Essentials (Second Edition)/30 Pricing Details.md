# Pricing Details

## Doc
* aws.amazon.com

## Acronym
* Std - Standard
* EBS - Elastic Block Store
* RDS - Relational Database Service
* EC2 - Elastic Compute Cloud
* S-IA - Standard-Infrequent Access
* CDN - Content Delievery Network

## Cost fundamentals 
* Pay for 
  * Compute capacity
  * Storage
  * Outbound data transfer (aggregated)
* No charge for
  * Inboud data transfer
  
## Serivce pricing for AWS offerings
* EC2
* S3
* EBS
* RDS
* CloudFront

### EC2
* Web service that
  * Provides resizable compute capacity in the cloud
  * Allows the configuration of capacity with minimal friction
  * Provides complete control
  * Charges only for capacity used
* Cost factors
  * Clock-second/hourly billing
    * Resources incur charges only when running
* Instance configuration
  * Physical capacity of the instance
  * Pricinfg varies with
    * AWS region
    * OS
    * Instance type
    * Instance size   
* Purchase types
  * On-demand instances
    * Compute capacity by the hour & second
    * Minimum of 60 seconds
  * Reserved instances
    * Low or no up-front payment instances reserved
    * Discount on hourly charge for that intance
  * Spot instances
    * Bid for unused Amazon EC2 capacity
* Other considerations
  * Number of instances
    * Provision multiple instnaces to hadnle peak loads
  * Load balancing
    * Use EBS to distribute traffic
    * Monthly cost based on
      * Hours load balancer runs
      * Data load balancer processes
* Product options
  * Monitoring
    * User Amazon CloudWatch to monitor instances
    * Basic monitoring (default)
    * Detailed monitoring (fixed rate; prorated partial months)
  * Auto Scaling
    * Automatically adjusts number of instances
    * No additional charge
  * Elastic IP Address
    * No charge when associated with a running instance
* OS & software
  * OS prices included in instance prices
  * Software
    * Partnership with other vendors
    * Vendor licences required
    * Existing licenses accepted through specific vendor programs

### S3
* What is S3
  * Object storage built to store & retrieve any amount of data from anywhere
  * Provides
    * Durability, availability, & scalability
    * Comprehensive security & compliance capabilities
    * Query in place
    * Flexible managemtnt & data transfer
    * Compatibility - supported by partners, vdendors, & AWS services
* Storage classess
  * Std storage
    * 99.999999999% durability
    * 99.99% availability
* Std-Infrequent Access (S-IA)
* Storage cost
  * Number & size objects
  * Type of storage
* Cost factors
  * Pricing based on
    * Requests
      * Number of requests
      * Type of requests - different rates for GET requests
    * Data transfer
      * Amount of data  transferred out of the Amazon S3 region

### EBS
* What is EBS
  * Block-level storage for instances
  * Volumes persist independently from the instance
  * Analogous to virtual disk in the cloud
  * 3 volume type
  * General purpose (SSD)
  * (Provisioned IOPS (SSD)
  * Magnetic
* Cost factors
  * Volumes: all types charged by the amount provisioned per month
  * IOPS
    * General Purpose (SSD): Included in price
    * Magnetic: Charged by the number of requests
    * Provisioned IOPS (SSD): Charged by the amount your provision in IOPS
  * Snapshots: Added cost per GB-month of data stored
  * Data transfer
    * Inbound data transfer has no charge
    * Outbound data transfer charges are tiered

### RDS
* What is RDS
  * Relational database in the cloud
  * Cost-efficient & resizable capacity
  * Management of time-consuming administrative tasks
* Cost factors
  * Clodk-hour billing: Resources incur charges when running
  * Database characteristics: Engine, size, & memory class impacts cost
  * DB purchase type
    * On-demand database instances are charged by the hour
    * Reserved database instances require up-front payment for database instances reserved
    * Provision multiple DB instances to handle peak loads
  * Provisionded storage
    * No charge for backup storage of up to 100% of database storage
    * Backup storage for terminated DB instances billed at GB/month
  * Additional storage: Backup storage in addition to provisioned storage billed at GB/month
  * Deplyment type
    * Storage & I/O charges variable
    * Single Availability Zones
    * Multiple Availability Zones
  * Data transfer
    * No charge for inbound data transfer
    * Tiered charges for outbound data transfer
    
### CloudFront
* What is Cloudfront
  * Web service for content delevery
  * Integration with other AWS services
    * Low latency
    * High data transfer speeds
    * No minimum commitments
* Cost factors
  * Pricing varies across geographic regions
  * based on
    * Requests
    * Data transfer out
* Wrap-up
  * Examine fundamental characteristics of product
  * Estimate usage
  * Map usage to prices
  
