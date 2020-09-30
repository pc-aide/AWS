# Caching & Caching Invalidations

## Doc
* [Invalidation](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/Invalidation.html)

## Acronym

## Intro
* Cache based on
    * Headers
    * Session Cookies
    * Query String Parameters
* The cache lives at each CloudFront **Edge Location**
* You want to mazimize the cache hit rate to minimize requests on the origin
* Control the TTL (0 seconds to 1 year), can be set by the origin using the Cache-Control header, Expires header...
* You can invalidate part of the cache using the **CreateInvalidation** API

### Diagram
[<img src="https://i.imgur.com/SIMSw61.png">](https://i.imgur.com/SIMSw61.png)

---

## Mazimize cahce hits by sperarating static & dynamic distributions
[<img src="https://i.imgur.com/b09yTri.png">](https://i.imgur.com/b09yTri.png)

---

## Demo
* Your S3 & CloudFront:

[<img src="https://i.imgur.com/77jCYS0.png">](https://i.imgur.com/77jCYS0.png)

* Edit CloudFront\Behaviors\TTL Setings:

[<img src="https://i.imgur.com/BGKiAy2.png">](https://i.imgur.com/BGKiAy2.png)

* if i update my index:
* we need wait our TTL:
````html
<p style="color: red;">
    new update in this section
</p>
````

[<img src="https://i.imgur.com/LQgp0hp.png">](https://i.imgur.com/LQgp0hp.png)
[<img src="https://i.imgur.com/ma6f5Qp.png">](https://i.imgur.com/ma6f5Qp.png)

* so to reflect our update code html in CloudFront, we need go to **create Invalidations**:
* This step said all CloudFront to flush their caches based on this **invalidations**:

[<img src="https://i.imgur.com/Plj9o9b.png">](https://i.imgur.com/Plj9o9b.png)
[<img src="https://i.imgur.com/GQOkzr2.png">](https://i.imgur.com/GQOkzr2.png)
[<img src="https://i.imgur.com/MmGtYyy.png">](https://i.imgur.com/MmGtYyy.png)

* Details:

[<img src="https://i.imgur.com/h6MXEuk.png">](https://i.imgur.com/h6MXEuk.png)

* F5:

[<img src="https://i.imgur.com/sl9CsFZ.png">](https://i.imgur.com/sl9CsFZ.png)

* but if i update again my content:

* My IDE:

[<img src="https://i.imgur.com/seJ5mCd.png">](https://i.imgur.com/seJ5mCd.png)

* MyBucket (OK):

[<img src="https://i.imgur.com/HAEK2pY.png">](https://i.imgur.com/HAEK2pY.png)

* MyCloudFront (no even after clear cachce & wait 5min):

[<img src="https://i.imgur.com/QmQEFxu.png">](https://i.imgur.com/QmQEFxu.png)
