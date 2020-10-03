# Quiz 12 - EB

## Questions
1) I am creating an application and would like for it to be running with minimal cost in a development environment. I should run it in
    * Single Instance Mode
    * HA Mode
* [Answer](https://i.imgur.com/Tm5EeyM.png)
2) Application versions can be deployed to 
    * One environment
    * Many environment
* [Answer](https://i.imgur.com/764KWY4.png)
3) I would like to customize the runtime of Elastic Beanstalk and include some of my company wide security software. I should
    * Provide an EC2 User Data script
    * Provide a custom platform
    * Provide a Docker image
* [Answer](https://i.imgur.com/EJOrvwM.png)
4) Environments in Elastic Beanstalk
    * Can be named freely
    * Hve to be named dev, test, prod
* [Answer](https://i.imgur.com/Z2zOzLw.png)
5) I would like to update my development environment as soon as a new version is available. Because
    my Elastic Beanstalk environment is internal and only used by me, I don't mind downtime. Which deployment options is the best fit?
    * All at once
    * Rolling
    * Rolling with batches
    * Immutable
* [Answer](https://i.imgur.com/yQghRgN.png)
6) I would like to update my Elastic Beanstalk application so that we are able to roll back very quickly in case of issues with the new
   application version. Which deployment mode is the best fit?
    * All at once
    * Rolling
    * Rolling with batches
    * Immutable
* [Answer](https://i.imgur.com/jm4qLs5.png)
7) I want to update my Elastic Beanstalk application gradually without incurring new costs on update. My application has been over
   provisioned and can temporarily decrease in size for the number of serving instances, but I still want to serve my
   users without downtime. I do not want to incur extra costs over updates. Which deployment mode is the best fit?
    * All at once
    * Rolling
    * Rolling with additional batches
    * Immutable
* [Answer](https://i.imgur.com/BLMXt7J.png)
8) We would like to update our EB application with minimal added cost, while maintaining the full capacity
   to serve our current users in production. Which deployment is the best fit?
    * All at once
    * Rolling 
    * Rolling with additional batches
    * Immutable
* [Answer](https://i.imgur.com/qtYchwT.png)
9) I would like to create an ElastiCache with my Elastic Beanstalk environment. I should
    * Create an ElastiCache instance manually outside of my EB & link to it through environement variables.
      Delete manually when done with the environment
    * Create an elasticache.ebextensions file at the root of the code zip file & provide appropriate configuration
    * Create a config.elasticache file in the .ebextensions filder which is at the root of the code zip file & provide
      appropriate configuration
    * Create an elasticache.config file in the .ebextension folder which is at the root of the code zip file & provide
      appropriate configuration
* [Answer](https://i.imgur.com/qVs6ZfQ.png)
10) My deployments on Elastic Beanstalk have been painfully slow, and after looking at the logs, I realize
    this is due to the fact that my dependencies are resolved on each EC2 machine at deployment time. How can
    I speed up my deployment with the minimal impact?
    * Remove some dependencies in your code
    * Place the dependencies in Amazon S3
    * Resolve the dependencies beforehand & package them in the zip file uploaded to EB
* [Answer](https://i.imgur.com/JpqftWr.png)
11) What service does Elastic Beanstalk use under the hood?
    * AWS OpsWork
    * AWS CloudFormation
    * AWS Lambda
* [Answer](https://i.imgur.com/7vU1U9B.png)
12) You would like your Elastic Beanstalk environment to expose an HTTPS endpoint instead of an HTTP endpoint in order to get in-flight
    encryption between your clients and your web servers. What must be done to setup HTTPS on Beanstalk?
    * Use a separate CloudFormation template to load the SSL certificate onto the LB
    * Create an .ebextension/elb.config file to foncfigre the LB
    * Open up the port 80 for the SG
    * Configure Health Checks
* [Answer](https://i.imgur.com/gy4HK9X.png)
13) How can you remove older versions that are not used by Elastic Beanstalk so that new versions can be created for your applications?
    * Setup an .ebextensions files
    * Use a Lifecycle Policy
    * Define a Lambda function
    * Use Worker Environments
* [Answer](https://i.imgur.com/v3TFtgp.png)
14) You are looking to perform a set of repetitive and scheduled tasks asynchronously. Which Elastic Beanstalk environment should you setup?
    * Setup a Web Server environment & a .ebextensions file
    * Setup a Web Server environement & a cron.yaml file
    * Setup a Worker environment & a .ebextensions file
    * Setup a Worker envrionment & a cron.yaml file
* [Answer](https://i.imgur.com/HE7OJh1.png)
15) You have created a test environment in Elastic Beanstalk and as part of that environment, you have created
    an RDS database. How can you make sure the database can be explored after the environment is destroyed?
    * Make a snapshot of the db before it gets deleted
    * Make a selective delete in EB
    * Change the EB envrionment variables
* [Answer](https://i.imgur.com/gQr0huA.png)
