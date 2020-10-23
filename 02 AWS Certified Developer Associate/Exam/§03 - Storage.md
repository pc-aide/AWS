# §03 - Storage.md

## Questions
1. You are developing an application that will run across dozens of instances. It uses some
components from a legacy application that requires some configuration files to be copied
from a central location and be held on a volume local to each of the instances. You
plan to modify your application with a new component in the future that will hold this
configuration in Amazon DynamoDB. However, in the interim, which storage option
should you use that will provide the lowest cost and the lowest latency for your application
to access the configuration files?
    * A. Amazon S3
    * B. Amazon EBS
    * C. Amazon EFS
    * D. Amazon EC2 instance store
2. In what ways does Amazon Simple Storage Service (Amazon S3) object storage differ from
block and file storage? (**Select TWO**.)
    * A. Amazon S3 stores data in fixed size blocks
    * B. Objects are identified by a numbered address.
    * C. Object can be any size.
    * D. Objects contain both data and metadata.
    * E. Objects are stored in buckets
3. You are restoring an Amazon Elastic Block Store (Amazon EBS) volume from a snapshot.
How long will it take before the data is available?
    * A. It depends on the provisioned size of the volume
    * B. The data will be available immediately
    * C. It depends on the amount of data stored on the volume
    * D. It depends on whether the attached instance is an Amazon EBS–optimized instance
4. What are some of the key characteristics of Amazon Simple Storage Service (Amazon S3)?
(**Select THREE**.)
    * A. All objects have a URL.
    * B. Amazon S3 can store unlimited amounts of data
    * C. Buckets can be mounted to the file system of multiple Amazon EC2 instances.
    * D. Amazon S3 uses a Representational State Transfer (REST) application program
interface (API).
    * E. You must pre-allocate the storage in a bucket.
5. Amazon S3 Glacier is well-suited to data that is which of the following? (**Select TWO**.)
    * A. Infrequently or rarely accessed
    * B. Must be immediately available when needed
    * C. Is available after a three- to five-hour restore period
    * D. Is frequently erased within 30 days
6. You have valuable media files hosted on AWS and want them to be served only to authenticated users of your web application. You are concerned that your content could be stolen
and distributed for free. How can you protect your content?
    * A. Use static web hosting.
    * B. Generate presigned URLs for content in the web application.
    * C. Use AWS Identity and Access Management (IAM) policies to restrict access
    * D. Use logging to track your content.
7. Which of the following are features of Amazon Elastic Block Store (Amazon EBS)?
(**Select TWO**.)
    * A. Data stored on Amazon EBS is automatically replicated within an Availability Zone.
    * B. Amazon EBS data is automatically backed up to tape
    * C. Amazon EBS volumes can be encrypted transparently to workloads on the attached
instance
    * D. Data on an Amazon EBS volume is lost when the attached instance is stopped.
8. Which option should you choose for Amazon EFS when tens, hundreds, or thousands of
Amazon EC2 instances will be accessing the file system concurrently?
    * A. General-Purpose performance mode
    * B. RAID 0
    * C. Max I/O performance mode
    * D. Change to a larger instance
9. Which of the following must be performed to host a static website in an Amazon Simple
Storage Service (Amazon S3) bucket? (**Select THREE**.)
    * A. Configure the bucket for static hosting, and specify an index and error document.
    * B. Create a bucket with the same name as the website.
    * C. Enable File Transfer Protocol (FTP) on the bucket.
    * D. Make the objects in the bucket world-readable
    * E. Enable HTTP on the bucket.
10. You have a workload that requires 1 TB of durable block storage at 1,500 IOPS during
normal use. Every night there is an extract, transform, load (ETL) task that requires 3,000
IOPS for 15 minutes. What is the most appropriate volume type for this workload?
    * A. Use a Provisioned IOPS SSD volume at 3,000 IOPS.
    * B. Use an instance store
    * C. Use a general-purpose SSD volume
    * D. Use a magnetic volume.
11. Which statements about Amazon S3 Glacier are true? (**Select THREE**.)
    * A. It stores data in objects that live in buckets.
    * B. Archives are identified by user-specified key names.
    * C. Archives take 3–5 hours to restore.
    * D. Vaults can be locked.
    * E. It can be used as a standalone service and as an Amazon S3 storage class.
12. You are developing an application that will be running on several hundred Amazon EC2
instances. The application on each instance will be required to reach out through a file
system protocol concurrently to a file system holding the files. Which storage option should
you choose?
    * A. Amazon EFS
    * B. Amazon EBS
    * C. Amazon EC2 instance store
    * D. Amazon S3
13. You need to take a snapshot of an Amazon Elastic Block Store (Amazon EBS) volume. How
long will the volume be unavailable?
    * A. It depends on the provisioned size of the volume.
    * B. The volume will be available immediately.
    * C. It depends on the amount of data stored on the volume.
    * D. It depends on whether the attached instance is an Amazon EBS–optimized instance.
14. Amazon Simple Storage Service (S3) bucket policies can restrict access to an Amazon S3
bucket and objects by which of the following? (**Select THREE**.)
    * A. Company name
    * B. IP address range
    * C. AWS account
    * D. Country of origin
    * E. Objects with a specific prefix
15. Which of the following are not appropriate use cases for Amazon Simple Storage Service
(Amazon S3)? (**Select TWO**.)
    * A. Storing static web content or hosting a static website
    * B. Storing a file system mounted to an Amazon Elastic Compute Cloud (Amazon EC2) instance
    * C. Storing backups for a relational database
    * D. Primary storage for a database
    * E. Storing logs for analytics
16. Which features enable you to manage access to Amazon Simple Storage Service (Amazon S3)
buckets or objects? (**Select THREE**.)
    * A. Enable static website hosting on the bucket.
    * B. Create a presigned URL for an object.
    * C. Use an Amazon S3 Access Control List (ACL) on a bucket or object.
    * D. Use a lifecycle policy.
    * E. Use an Amazon S3 bucket policy.
17. Your application stores critical data in Amazon Simple Storage Service (Amazon S3),
which must be protected against inadvertent or intentional deletion. How can this data be
protected? (**Select TWO**.)
    * A. Use cross-region replication to copy data to another bucket automatically.
    * B. Set a vault lock
    * C. Enable versioning on the bucket.
    * D. Use a lifecycle policy to migrate data to Amazon S3 Glacier.
    * E. Enable MFA Delete on the bucket.
18. You have a set of users that have been granted access to your Amazon S3 bucket. For
compliance purposes, you need to keep track of all files accessed in that bucket. To have a
record of who accessed your Amazon Simple Storage Service (Amazon S3) data and from
where, what should you do?
    * A. Enable versioning on the bucket.
    * B. Enable website hosting on the bucket.
    * C. Enable server access logging on the bucket.
    * D. Create an AWS Identity and Access Management (IAM) bucket policy.
    * E. Enable Amazon CloudWatch logs.
19. What are some reasons to enable cross-region replication on an Amazon Simple Storage
Service (Amazon S3) bucket? (**Select THREE**.)
    * A. Your compliance requirements dictate that you store data at an even further distance
than Availability Zones, which are tens of miles apart.
    * B. Minimize latency when your customers are in two geographic regions.
    * C. You need a backup of your data in case of accidental deletion
    * D. You have compute clusters in two different AWS Regions that analyze the same set of objects.
    * E. Your data requires at least five nines of durability.
20. Your company requires that all data sent to external storage be encrypted before being sent.
You will be sending company data to Amazon S3. Which Amazon Simple Storage Service
(Amazon S3) encryption solution will meet this requirement?
    * A. Server-Side Encryption with AWS managed keys (SSE-S3)
    * B. Server-Side Encryption with customer-provided keys (SSE-C)
    * C. Client-side encryption with customer-managed keys
    * D. Server-side encryption with AWS Key Management Service (AWS KMS) keys (SSE-KMS)
21. How is data stored in Amazon Simple Storage Service (Amazon S3) for high durability?
    * A. Data is automatically replicated to other regions.
    * B. Data is automatically replicated within a region.
    * C. Data is replicated only if versioning is enabled on the bucket.
    * D. Data is automatically backed up on tape and restored if needed.
* [Answers]()
* Score: 
