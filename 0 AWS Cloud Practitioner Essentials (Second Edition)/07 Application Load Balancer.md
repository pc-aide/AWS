# Application Load Balancer

## Acronym
* WAF - Web Application Firewall
* ElB - Elastic Loab Balacing
* ALB - Application Load Balancer
* Cfg - Configuration
* VPC - Virtual Private Cloud

## Terminology
* Scheme (cfg load balancer)
  * An Internet-facing load balancer routes requests from clients over
    the internet to targets. An internal load balancer rutes requests
    from cleints to targets using private IP addresses.
* Listeners
  * A listener is a process that checks for connection requests,
    using the protocol & port that you configure. The rules that
    you define for a listener determine how the load balancer
    routes request to the targets in one or more target groups.
* Target
  * A target is a destination for traffic based on the established
    listener rules.
* Target Group
  * Each target group routes requests to one or more registered
    targets using the protocol & port number specified.
    A target can be registered with multiple target groups.
    Health checks can be configured on a per target group basis.

## Ports 
* 80 - HTTP
* 8080 - Alternative port for HTTP. See also ports 80 and 8080
* 3306 - MySQL database system

## Topology
[<img src="https://i.imgur.com/26Z96zL.png">](https://i.imgur.com/26Z96zL.png)

## Features
* Supported Protocols
  * HTTP, HTTPS, HTTP/2, & WebSockets
* CloudWatch Metrics
  * addtitional load balance metrics & Target Group metric dimension
* Access Logs
  * Ability to see connection details for WebSocket connections
* Health Checks
  * Insight into target & application
    * E.g
      * Check
        * Protocol : HTTP
        * Path : /test.html

## Addtional Features
[<img src="https://i.imgur.com/kXctbMi.png">](https://i.imgur.com/kXctbMi.png)

## Use Cases
* Ports

[<img src="https://i.imgur.com/z3tdRtd.png">](https://i.imgur.com/z3tdRtd.png)

* Listener + Target + Target Group

[<img src="https://i.imgur.com/JlSIMpA.png">](https://i.imgur.com/JlSIMpA.png)

## E.g
### AWS Console
* EC2\Instance\CentOS7

[<img src="httpshttps://i.imgur.com/b5H05Be.png">](https://i.imgur.com/b5H05Be.png)

#### Port 80
[<img src="https://i.imgur.com/TF2caXJ.png">](https://i.imgur.com/TF2caXJ.png)

#### Port 8080
[<img src="https://i.imgur.com/ufV6Eow.png">](https://i.imgur.com/ufV6Eow.png)

### Create Application Load Balancer
* EC2\Instance\Load Balancers

[<img src="https://i.imgur.com/Oei8E79.png">](https://i.imgur.com/Oei8E79.png)

* Create Load Balancer\**Application Load Balancer**

[<img src="https://i.imgur.com/BtwOpgS.png">](https://i.imgur.com/BtwOpgS.png)

#### Cfg 
##### Basic
* Name
* Scheme
  * internet-facing
  * internal
* IP addresses type
  * ipv4
  * dualstack (IPv4 & IPv6)
  
[<img src="https://i.imgur.com/uNjb1Cs.png">](https://i.imgur.com/uNjb1Cs.png)
  
##### Listeners
1) http | port 80
2) http | port 8080

[<img src="https://i.imgur.com/E7llZHu.png">](https://i.imgur.com/E7llZHu.png)

##### Availability Zones
1) VPC
  * us-east-2b
  * us-east-2c
  
[<img src="https://i.imgur.com/yogwWSr.png">](https://i.imgur.com/yogwWSr.png)
  
##### Tags
* Apply tags to your load balancer to help organize & identify them
1) key
  * Name
  
2) Value
  * Application Load Balancer
  
#### Config Security Settings
[<img src="https://i.imgur.com/NGvH8Vc.png">](https://i.imgur.com/NGvH8Vc.png)

#### Config Security groups
[<img src="https://i.imgur.com/MkP6IL4.png">](https://i.imgur.com/MkP6IL4.png)

#### Config Routing
* A routing rule for the backed destination for your load balancer

##### Target group
* Target group
  * New target group
* Name
  * demo1
* Target type
  * Instance
  * IP
  * Lambda function
* Protocol
  * HTTP
* Port
  * 80
  
[<img src="https://i.imgur.com/C2RTVIb.png">](https://i.imgur.com/C2RTVIb.png)
  
##### Health checks
* Protocol
* Path
  * /
  
##### Adv health check settings
* Port
  * traffic port
  * override
* Healthy threshold
* Unhealthy threshold
* Timeout
* Interval
* Success codes (HTTP codes)

[<img src="https://i.imgur.com/4XW6deM.png">](https://i.imgur.com/4XW6deM.png)

#### Register Targets
* add to registered on port 80

[<img src="https://i.imgur.com/tTuzKp0.png">](https://i.imgur.com/tTuzKp0.png)

#### Review
[<img src="https://i.imgur.com/CC8OpX4.png">](https://i.imgur.com/CC8OpX4.png)

## Target Groups
* We have two targets (port 80 & port 8080) that we want
  to check with this load balancer in order to register the 
  second target, we first create a target group
  
* Load Balancers\**Rarget Groups**

[<img src="https://i.imgur.com/rjWT1mA.png">](https://i.imgur.com/rjWT1mA.png)

### Create target group
* second container (8080)

#### Target group (second)
* Target group name
  * demo2
  * Protocol
   * HTTP
  * Port
   * 8080
  * VPC

[<img src="https://i.imgur.com/4Na9AOm.png">](https://i.imgur.com/4Na9AOm.png)

#### Health check settings (second)
* Protocol
* Paht
* port
  * traffic port
  * override

[<img src="https://i.imgur.com/5wKIlKn.png">](https://i.imgur.com/5wKIlKn.png)

#### Registered (second)
[<img src="https://i.imgur.com/KnVvLBN.png">](https://i.imgur.com/KnVvLBN.png)

## Check UP
* Load Balancers\Listeners

[<img src="https://i.imgur.com/vLjzjsU.png">](https://i.imgur.com/vLjzjsU.png)

### demo1 (listener 8080)
* default
* change to demo2
  * edit rule

[<img src="https://i.imgur.com/rfGkKKF.png">](https://i.imgur.com/rfGkKKF.png)

#### Edit rule
[<img src="https://i.imgur.com/Iawh5GM.png">](https://i.imgur.com/Iawh5GM.png)

## Test
* copy DNS name

### Container 01
[<img src="https://i.imgur.com/WqKnXN1.png">](https://i.imgur.com/WqKnXN1.png)
