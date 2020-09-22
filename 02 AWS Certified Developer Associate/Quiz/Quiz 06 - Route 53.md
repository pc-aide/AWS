# Quiz 06 - Route 53

## Questions
1) You have purchased "mycoolcompany.com" on the AWS registrar and would like for it to point
to **lb1-1234.us-east-2.elb.amazonaws.com** . What sort of Route 53 record is NOT POSSIBLE to set up for this?
    * CNAME
    * Alias
* [Answer](https://i.imgur.com/hMCAlw4.png)
2) You have deployed a new Elastic Beanstalk environment and would like to direct 5% of your production
   traffic to this new environment, in order to monitor for CloudWatch metrics and ensuring no bugs exist. What type of Route 53 records allows you to do so?
   * Simple
   * Weighted
   * Latency
   * Failover
* [Answer](https://i.imgur.com/GNT9SuJ.png)
3) After updating a Route 53 record to point "myapp.mydomain.com" from an old Load Balancer to a new load balancer,
   it looks like the users are still not redirected to your new load balancer. You are wondering why...
   * It's because of the alis record
   * It's because of the CNAME record
   * It's because of the TTL
   * It's because of the health checks
* [Answer](https://i.imgur.com/G9gK9Mj.png)
4) You want your users to get the best possible user experience and that means minimizing the response time
   from your servers to your users. Which routing policy will help?
   * Multi value
   * Weighted
   * Latency
   * Geo location
* [Answer](https://i.imgur.com/yzFok47.png)
5) You have a legal requirement that people in any country but France should not be able to access your website. Which Route 53 record helps you in achieving this?
   * Latency
   * Simple
   * Geolocation
   * Multi value
* [Answer](https://i.imgur.com/HTymhRY.png)
