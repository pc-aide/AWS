# Quiz 03 - Fundamentals 2

## Questions
1) Load Balancers provide a 
    * static IPv4 we can use in our application
    * static DNS name we can use in our application
    * static ipv6 we can use in our application
* [Answer](https://i.imgur.com/HWp2Ey2.png)
2) You are running a website with a load balancer and 10 EC2 instances. Your users are
   complaining about the fact that your website always asks them to re-authenticate when
   they switch pages. You are puzzled, because it's working just fine on your machine and in the dev environment with 1 server. What could be the reason?
   * The application must have a bug
   * The Load Balancer does not have stickiness enabled
   * The EC2 instances log out users because they don't see their true IPs
* [Answer](https://i.imgur.com/yRRmzSy.png)
3) Your application is using an Application Load Balancer. It turns out your application
   only sees traffic coming from private IP which are in fact your load balancer's. What
   should you do to find the true IP of the clients connected to your website?
   * Modify the front-end of the website so that the users send their IP in thre requests
   * Look into the X-Forwarded-For header in the backend
   * Look into the X-Forwarded-Proto header in the backend
* [Answer](https://i.imgur.com/SP7VWgt.png)
4) You quickly created an ELB and it turns out your users are complaining about the fact that
   sometimes, the servers just don't work. You realise that indeed, your servers do crash from
   time to time. How to protect your users from seeing these crashes?
   * Enable stickiness
   * Enable health checks
   * Enable SSL termination
* [Answer](https://i.imgur.com/b9yiJwQ.png)
5) You are designing a high performance application that will require millions of connections
   to be handled, as well as low latency. The best Load Balancer for this is
   * Application Load Balancer
   * Classic Load Balancer
   * Netowork Load Balancer
* [Answer](https://i.imgur.com/LKUQb1B.png)
6) Application Load Balancers handle all these protocols except
   * HTTP
   * HTTPS
   * WebSockert
   * TCP
* [Answer](https://i.imgur.com/z8PRK7Q.png)
7) The application load balancer can redirect to different target groups based on all these except...
   * Hostname
   * Request Path
   * client IP
* [Answer](https://i.imgur.com/VH0UkZ1.png)
8) You are running at desired capacity of 3 and the maximum capacity of 3.
   You have alarms set at 60% CPU to scale out your application. Your application is now running at 80% capacity. What will happen?
   * Nothing
   * The desired capacity will go up to 4 & the maximum will stay at 3
   * The desired cpacity will go up to 4 & the maximum will stay at 4
* [Answer](https://i.imgur.com/m6h15PR.png)
9) I have an ASG and an ALB, and I setup my ASG to get health status of instances
   thanks to my ALB. One instance has just been reported unhealthy. What will happen?
   * The ASG will keep the instance running & re-start the application
   * The ASG will detach the EC2 instance from the group, & leave it running
   * The ASG will terminate the EC2 instance
* [Answer](https://i.imgur.com/M72r6aV.png)
10) Your boss wants to scale your ASG based on the number of requests per minute your application makes to your database. 
   * You plitely tell him it's impossible
   * You create a CloudWatch custom metric & build an alarm on this to scle your ASG
   * You enable detailed monitoring & use that to scale your ASG
* [Answer](https://i.imgur.com/Bkg6mfN.png)
11) Scaling an instance from an r4.large to an r4.4xlarge is called
   * Horizontal Scalability
   * Vertical Scalability
* [Answer](https://i.imgur.com/0JUXnUc.png)
12) Running an application on an auto scaling group that scales the number of instances in and out is called
   * Vertical Scalability
   * Horizontal Scalability
* [Answer](https://i.imgur.com/CkeDSfw.png)
13) You would like to expose a fixed static IP to your end-users for compliance
    purposes, so they can write firewall rules that will be stable and approved by regulators. Which Load Balancer should you use?
   * Application Load Balancer with Elatic IP attached to it
   * Network Load Balancer
   * Classic Load Balancer
* [Answer](https://i.imgur.com/uI5WnGg.png)
14) A web application hosted in EC2 is managed by an ASG. You are exposing this application
    through an Application Load Balancer. The ALB is deployed on the VPC with the following
    CIDR: 192.168.0.0/18. How do you configure the EC2 instance security group to ensure only the ALB can access the port 80?
   * Open up the EC2 security group on port 80 to 0.0.0.0/0
   * Open up the EC2 security group on port 80 to 192.168.0.0/18
   * Open up the EC2 security group on port 80 to ALB's security group
* [Answer](https://i.imgur.com/ghXNKNA.png)
15) Your application load balancer is hosting 3 target groups with hostnames being users.example.com
    , api.external.example.com, and checkout.example.com. You would like to expose HTTPS traffic for
    each of these hostnames. How do you configure your ALB SSL certificates to make this work?
   * Use SNI
   * Use a wildcard SSL certificate
   * Use an HTTP to HTTPS redirect rule
   * Use a security group SSL certificate
* [Answer](https://i.imgur.com/VSVghnD.png)
16) The Application Load Balancers target groups can be all of these EXCEPT...
   * EC2 Instances
   * IP Addresses
   * Lambda Functions
   * Network Load Balancer
* [Answer](https://i.imgur.com/jYIV3vb.png)
17) You are running an application in 3 AZ, with an Auto Scaling Group and a Classic Load Balancer.
    It seems that the traffic is not evenly distributed amongst all the backend EC2 instances,
    with some AZ being overloaded. Which feature should help distribute the traffic across all the available EC2 instances?
   * Stickiness
   * Cross Zone Load Balancing
   * Target Group Routing Rules
   * HTTPS termination
* [Answer](https://i.imgur.com/DNNiXYl.png)
18) Your Application Load Balancer (ALB) currently is routing to two target groups,
    each of them is routed to based on hostname rules. You have been tasked with enabling
    HTTPS traffic for each hostname and have loaded the certificates onto the ALB. Which ALB
    feature will help it choose the right certificate for your clients?
   * TLS Termination
   * Server Name Indication (SNI)
   * SSL Security Policies
   * Host Header
* [Answer](https://i.imgur.com/iVqXmxb.png)
19) An application is deployed with an Application Load Balancer and an Auto Scaling Group.
    Currently, the scaling of the Auto Scaling Group is done manually and you would like to
    define a scaling policy that will ensure the average number of connections to your EC2
    instances is averaging at around 1000. Which scaling policy should you use?
   * Simple Scaling Policy
   * Step Scaling Policy
   * Target Tracking
   * Scheduled Scaling
* [Answer](https://i.imgur.com/obqw5nY.png)
