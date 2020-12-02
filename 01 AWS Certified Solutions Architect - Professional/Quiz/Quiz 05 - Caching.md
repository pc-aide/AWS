# Quiz 05 - Caching

## Questions
1) You have deployed the same SSL certificate onto your CloudFront and ALB. You would like to ensure you get a high ratio of cache hit but also don't want to break SSL. What do you recommend? 
   * A. Forwarded the Host header
   * B. Remove the Host header
2) You would like to ensure your ALB is only accessible through a CloudFront distribution so that you can protect the content accessible to your users. What do you recommend?
   * A. Make your ALB public. Add the private CloudFront IP to your ALB SG & create CloudFront signed URLs
   * B. Make your ALB public. Add the public CloudFront IP to your ALB SG & create CloudFront signed URL
   * C. Make your ALB private. Add the private CloudFront IP to your ALB SG & create CloudFront signed URLs
   * D. Make your ALB private. Add the public CloudFront IP to your ALB SG & create CloudFront signed URL
3) Which ElastiCache cache technology will give you a deployment that can survive the loss of an AZ without data loss? 
   * A. Redis
   * B. Memcached
* [Answers](https://i.imgur.com/g3AEFxT.png)
* Score:
  * [02-12-2020 PM] 3/3 = 100%
