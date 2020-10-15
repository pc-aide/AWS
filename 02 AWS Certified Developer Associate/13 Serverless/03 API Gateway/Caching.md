# Caching

## Doc

## Acronym
* TTL - Time To Live
* IAM - Identity & Access Management

## Caching API responses
* Caching reduces the number of calls made to the backend
* Default **TTL**  is 300s (5m) (min: 0s, max: 3600s (1h))
* **Caches are defined per stage**
* Possible to override cache settings **per method**
* Cache encryption option
* Cache capacity between 0.5 GB to 237 GB
* **Cache is expensive**, makes sense in production, may not make sense in dev/test

### Diagram
[<img src="https://i.imgur.com/hyDjf8l.png">](https://i.imgur.com/hyDjf8l.png)

---

## Cache Invalidation
* Able to flush the entire cache (invalidate it) immediately
* Clients can invalidate the cache with **header:Cache-Control:max-age=0** (with proper IAM authorization)
* IAM policy:
````json
{
    "version": "2012-10-17",
    "Statemenet": [
        {
            "Effect": "Allow",
            "Action": [
                "execute-api:InvalidateCache"
            ],
            "Resource": [
                "arn:...:api-id/stage-name/GET/resource-path-specifier"
            ]
        }
    ]
}
````
* If you don't impose an InvalidateCache policy (or choose the Require authorization check box in the
  console), any client can invalidate the API cache
    * that could be a **disaster**
    
---

## Demo
*  API Gateway\stages
    * prod\Settings
    * CheckBox: Enable API cache - warning $$$ not free
    * Cache capacity: 0.5GB
      * min 0.5GB & max: 237GB
    * CheckBox: Encrypt cache data
    * Cache TTL: 60s
    * Per-key cache invalidation
      * CheckBox: Require authorization
* Save changes

[<img src="https://i.imgur.com/Cr0JRMR.png">](https://i.imgur.com/Cr0JRMR.png)
[<img src="https://i.imgur.com/d9GCowk.png">](https://i.imgur.com/d9GCowk.png)

---

## Setting cache each meathod
* Example: Stage/prod/houses
    * GET
    * Override for this method
      * Cache Setting
      
[<img src="https://i.imgur.com/5KfunOc.png">](https://i.imgur.com/5KfunOc.png)

* Browser\F5 to check the cache

[<img src="https://i.imgur.com/b9iOFTC.png">](https://i.imgur.com/b9iOFTC.png)
[<img src="https://i.imgur.com/oMPerpR.png">](https://i.imgur.com/oMPerpR.png)
