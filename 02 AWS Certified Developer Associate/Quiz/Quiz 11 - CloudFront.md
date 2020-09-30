# Quiz 11 - CloudFront

## Questions
1) Which features allows us to distribute paid content from S3 securely, globally, if the S3 bucket is secured to only exchange data with CloudFront?
    * Origin Access Identity
    * S3 Pre-Signed URL
    * CloudFront Signed URL
    * CloudFront Distribution Invalidations
* [Answer](https://i.imgur.com/WF8CuaN.png)
2) You are hosting highly dynamic content in Amazon S3 in us-east-1. Recently, there has been a need to make
   that data available with low latency in Singapore. What do you recommend using?
    * CloudFront
    * S3 Cross Region Replication
    * S3 Pre-Signed URLs
* [Answer](https://i.imgur.com/nGHpVu6.png)
3) How can you ensure that only users who access our website through Canada are authorized in CloudFront?
    * Set up a security group & attach it to CloudFront
    * Use a Route 53 Latency record & attach it to CloudFront
    * Use CloudFront Geo Restriction
* [Answer](https://i.imgur.com/TZ0Uh1Q.png)
4) CloudFront is deploying in front of an HTTP origin. After updating your HTTP app, the users still see the old website. What should you do?
    * Disable caching
    * Invalidate the distribution
    * Recreate a distribution
* [Answer](https://i.imgur.com/HfmB4op.png)
