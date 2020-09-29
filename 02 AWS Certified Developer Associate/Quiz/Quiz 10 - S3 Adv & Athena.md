# Quiz 10 - S3 Adv & Athena.md

## Questions
1) You have enabled versioning and want to be extra careful when it comes to deleting files on S3.
   What should you enable to prevent accidental permanent deletions?
   * Use a bucket policy
   * Enable MFA Delete
   * Encrypt the files
   * Disable versioning
* [Answer](https://i.imgur.com/3vPXgbW.png)
2) You would like all your files in S3 to be encrypted by default. What is the optimal way of achieving this?
   * Use a Bucket Policy that forces HTTPS connections
   * Enable "Default Encryption" on S3
   * Enable versioning
* [Answer](https://i.imgur.com/z3Fniz2.png)
3) You suspect some of your employees to try to access files in S3 that they don't have access to.
   How can you verify this is indeed the case without them noticing?
   * Restrict their IAM policies & look at CloudTrails logs
   * Enable S3 Access Logs & analyze them using Athena
   * Use a bucket policy
* [Answer](https://i.imgur.com/2C1H63t.png)
4) You are looking for your entire S3 bucket to be available fully in a different region so you can perform
   data analysis optimally at the lowest possible cost. Which feature should you use?
   * CloudFront distributions
   * S3 Cross-Region Replication
   * S3 Versioning
   * S3 Websites
* [Answer](https://i.imgur.com/BoUeK5z.png)
5) You are looking to provide temporary URLs to a growing list of federated users in order to
   allow them to perform a file upload on S3 to a specific location. What should you use?
   * S3 CORS
   * S3 Pre-Signed URL
   * S3 Bucket Policies
   * IAM Users
* [Answer](https://i.imgur.com/grK6VjW.png)
6) Which of the following is NOT a Glacier retrieval mode?
   * Instant (10 seconds)
   * Expedited (1 to 5 minutes)
   * Standard (3 to 5 hours)
   * Bulk (5 to 12 hours)
* [Answer](https://i.imgur.com/7TYaag8.png)
7) Which of the following is a Serverless data analysis service allowing you to query data in S3?
   * S3 Analytics
   * Athena
   * Redshift
   * RDS
* [Answer](https://i.imgur.com/kZ1iMux.png)
8) You would like to retrieve a subset of your dataset stored in S3 with the CSV format.
   You would like to retrieve a month of data and only 3 columns out of the 10. You need
   to minimize compute and network costs for this, what should you use?
   * S3 Select
   * S3 Inventory
   * S3 Analytics
   * S3 Access Logs
* [Answer](https://i.imgur.com/p4GAgli.png)
9) You're trying to upload a 25 GB file on S3 and it's not working
   * The limit of file size on S3 is 5GB
   * The S3 service must be down
   * You should use Multi Part upload when your file is bigger than 5GB
* [Answer](https://i.imgur.com/rRkoN9Q.png)
10) When uploading a file that is 1 GB to S3, which type of upload will give you the best throughput performance and resilience?
   * Upload as one part
   * Do a multi-part upload
   * Use SSE-S3
* [Answer](https://i.imgur.com/J12Rd67.png)
