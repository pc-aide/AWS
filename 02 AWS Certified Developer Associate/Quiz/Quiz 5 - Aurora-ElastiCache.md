# Quiz 5 - Aurora-ElastiCache

## Questions
1) My company would like to have a MySQL database that is going to be available even in case of a disaster in the AWS Cloud. I should setup 
    * Read Replicas
    * Encryption
    * Multi AZ
* [Answer](https://i.imgur.com/OWud058.png)
2) Our RDS database struggles to keep up with the demand of the users from our website.
   Our million users mostly read news, and we don't post news very often. Which solution will NOT help fix this problem?
   * An ElastiCache cluster
   * RDS Read Replicas
   * RDS Multi AZ
* [Answer](https://i.imgur.com/YTZUQl3.png)
3) We have setup read replicas on our RDS database, but our users are complaining
   that upon updating their social media posts, they do not see the update right away
   * There must be a bug in our application
   * Read Replicas have asynchronous replication & therefore it's likely our users will only observe eventual consistency
   * We should have setup multi-az instead
* [Answer](https://i.imgur.com/6wO7DIj.png)
4) Which RDS Classic (not Aurora) feature does not require us to change our SQL connection string?
    * Read Replicas
    * Multi AZ
* [Answer](https://i.imgur.com/OKObN8D.png)
5) You want to ensure your Redis cluster will always be available
    * Enable Read Replicas
    * Enable Multi AZ
* [Answer](https://i.imgur.com/sF0AXB7.png)
6) Your application functions on an ASG behind an ALB. Users have to constantly log back
   in and you'd rather not enable stickiness on your ALB as you fear it will overload some servers. What should you do?
   * Create your own Load Balancer & deploy that on EC2 instances
   * Store session data in RDS
   * Store session data in ElastiCache
   * Store session data in a shared EBS volume
* [Answer](https://i.imgur.com/ck9HnMv.png)
7) One analytics application is currently performing its queries against your main
   production database. These queries slow down the database which impacts the main user experience. What should you do to improve the situation?
   * Setup a Read Replica
   * Setup Multi Az
   * Run the analytics queries at night
   * Increase the RDS instance size
* [Answer](https://i.imgur.com/V0r9LHr.png)
8) You have a requirement to use TDE (Transparent Data Encryption) on top of KMS. Which database technology does NOT support TDE on RDS?
    * PostgreSQL
    * Oracle
    * MS SQL Server
* [Answer](https://i.imgur.com/DMFoJxP.png)
9) Which RDS database technology does NOT support IAM authentication?
    * Oracle
    * PostgreSQL
    * MySQL
* [Answer](https://i.imgur.com/HVgCgog.png)
10) You would like to ensure you have a database available in another region if a disaster happens to your main region. Which database do you recommend?
    * RDS with REad Replicas in another AZ
    * RDS with Multi AZ
    * Aurora Read Replicas in another AZ
    * Aurora Global Database
* [Answer](https://i.imgur.com/iaB02h3.png)
11) You are managing a PostgreSQL database and for security reasons, you would
    like to ensure users are authenticated using short-lived credentials. What do you suggest doing?
    * Install PostgreSQL on EC2 & install the pg_iam module. Authenticate using IAM username & password
    * Use PostgreSQL for RDS & install the pg_iam module. Authenticate using IAM username & password
    * Use PostegreSQL for RDS & authenticate using a toke obtained through the RDS service
    * Use PostgreSQL for RDS & force SSL connections. Authenticate using SSL certificates that you regularly rotate
* [Answer](https://i.imgur.com/a2GT3oZ.png)
12) Your organisation wants to enforce SSL connections on your MySQL database
    * Change your security group rules to only allow SSL traffic
    * Download certificate & change your application to connect using SSL
    * Apply a 'REQUIRE SSL' statement to all your users in your SQL database
    * Enable RDS encryption
* [Answer](https://i.imgur.com/e9I8VBt.png)
13) You are implementing a caching strategy with ElastiCache and would like to ensure
    that only the data that is often requested will be loaded in ElastiCache, as your cache size is small. Which caching strategy should you implement?
    * Lazy Loading
    * Write Through
    * TTL
* [Answer](https://i.imgur.com/NHO0nS8.png)
14) You are serving web pages for a very dynamic website and you have a requirement to keep
    latency to a minimum for every single user when they do a read request. Writes can take longer to happen. Which caching strategy do you recommend?
    * Cache aside
    * Write-through
    * TTL
* [Answer](https://i.imgur.com/TQ2QJir.png)
