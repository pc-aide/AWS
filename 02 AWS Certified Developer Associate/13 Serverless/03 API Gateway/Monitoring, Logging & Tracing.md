# Monitoring, Logging & Tracing

## Acronym
* CW - CloudWatch
* rps - request per seconds
* WAF - Web Application Firewall

## Doc

## Logging & Tracing
* CW Logs:
    * Enable CW logging at  the Stage level (with Log Level)
    * Can override settings on a per API basis (ex: ERROR, DEBUG, INFO)
    * Log contains information about request/response body
* X-Ray
    * Enable tracing to get extra information about requests in API Gateway
    * X-Ray API Gateway + Lambda gives you the full picture
    
---

## CW Metrics
* Metrics are by stage, Possibility to enable to detailed metrics
* **CacheHitCount & CacheMissCount**: efficiency of the cache
* **Count**: The total number API requests in a given period
* **IntegrationLatency**: The timme between when API Gateway relays a request to the backend & when it
  receives a response from the backend
* **Latency**: The time between when API Gateway receives a request from a client & when it returns
  a response to the client. The latency includes the integration latency & other API Gateway overhead
* **4XXError** (client-side) & **5XXError** (server-side)

---

## Throttling
* Account Limit
    * API Gateway throttles requests at 10k rps across all API
    * Soft limit that can be increased upon request
* In case of throttling => **429 Too Many Requests** (retriable error)
* Can set **Stage limit & Method limits** to improve performance
* Or you can define **Usage Plans** to throttle per customer
* Just like Lambda Concurrency, one API that is overloaded, if not limited can cause the other APIs
  to be throttled
  
---

## Errors
* 4xx means Client errors
    * ex:
      * 400 Bad Request
      * 403 Forbidden, WAF filtered
      * 404 Not found
      * 429 Many requests
* 5xx means Server errors (backend)
    * ex:
      * **502 Bad Gateway**, Exception, usually for an incomptable output returned from a Lambda proxy
        integration backed & occasionally for out-of-order invocations due to heavy loads
      * 503 Service Unavailable Exception
      * 504 Integration Failue - ex Endpoint Request Timed-out Exception **APi Gateway requests time out after 29 second maximum**
