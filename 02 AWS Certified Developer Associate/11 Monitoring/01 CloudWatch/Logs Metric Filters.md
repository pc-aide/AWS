# Logs Metric Filters

## Acronym
* CW - CloudWatch
* SNS - Simple Notification Service

## Terminology
* [Code http method](https://www.restapitutorial.com/httpstatuscodes.html)
    * 2xx Success
        * 200 OK
    * 4xx Client error
        * 400 Bad Request

## Doc
* [Filter and Pattern Syntax](https://docs.aws.amazon.com/AmazonCloudWatch/latest/logs/FilterAndPatternSyntax.html)

## Intro
* CloudWatch Logs can use filter expressions
    * For example, find a specific IP inside of a log
    * Or count occurrences of "ERROR" in your logs
    * Metric filters can be used to trigger alarms
* Filters don't retroactively filter data. Filters only publish the metric data points for events that happen after the filter was created

### Diagram
[<img src="https://i.imgur.com/LOBg6YV.png">](https://i.imgur.com/LOBg6YV.png)

---

## Demo
* CloudWatch\Log groups\
    * nginx/access.log
    
[<img src="https://i.imgur.com/M6Ozs70.png">](https://i.imgur.com/M6Ozs70.png)

* log stream\\<take any one\>
* Filter events\ 
    * 400

[<img src="https://i.imgur.com/JQGpgbN.png">](https://i.imgur.com/JQGpgbN.png)
[<img src="https://i.imgur.com/RqDdy52.png">](https://i.imgur.com/RqDdy52.png)
[<img src="https://i.imgur.com/GoF818M.png">](https://i.imgur.com/GoF818M.png)

* Create filter metric 
* i don't have any error 404 on website (log streams)
    * example: forced bad request (http://beanstalk-test.com/data-user/lates/test.html)

[<img src="https://i.imgur.com/0v7MjO3.png">](https://i.imgur.com/0v7MjO3.png)
[<img src="https://i.imgur.com/6uXJMT5.png">](https://i.imgur.com/6uXJMT5.png)
[<img src="https://i.imgur.com/YYn4dDR.png">](https://i.imgur.com/YYn4dDR.png)

* Create metric filter
    * Filter pattern: 400
    * Test pattern: 0 match
    * Filter name: Metric-Filter-400
    * Metric namespace: Metric-Filters
    * Metric name: Demo-Filter
    * Metric value: 1
    * Default value: 0
    
[<img src="https://i.imgur.com/YZc2ABp.png">](https://i.imgur.com/YZc2ABp.png)
[<img src="https://i.imgur.com/y5LvKBo.png">](https://i.imgur.com/y5LvKBo.png)
[<img src="https://i.imgur.com/nuUuR7w.png">](https://i.imgur.com/nuUuR7w.png)
[<img src="https://i.imgur.com/8INYFk8.png">](https://i.imgur.com/8INYFk8.png)

* EB\Restart srv:
* get new metric in CW
    * no value into

[<img src="https://i.imgur.com/9WFd0J1.png">](https://i.imgur.com/9WFd0J1.png)
[<img src="https://i.imgur.com/xhXoHlK.png">](https://i.imgur.com/xhXoHlK.png)
[<img src="https://i.imgur.com/sHS4BVK.png">](https://i.imgur.com/sHS4BVK.png)

* create an alarm on custom metric

[<img src="https://i.imgur.com/jYwk6HQ.png">](https://i.imgur.com/jYwk6HQ.png)
