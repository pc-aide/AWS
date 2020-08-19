# Application Load Balancer

## Acronym
* WAF - Web Application Firewall
* L

## Terminology
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
