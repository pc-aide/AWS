# ElastiCache Strategies

## Doc
* [Caching Best Practices](https://aws.amazon.com/caching/best-practices/)

## Acronym
* DB - Database
* TTL - Time-To-Live
* LRU - Least Recently User

## Caching Implementation Considerations
* Is it safe to cache data? Data may be out of date, eventually consistent
* Is caching effective for that data?
    * Pattern: data changing slowly, few keys are frequently needed
    * Anti patterns: data chinging rapidly, all large key space frequently needed
* Is data structured well for caching?
    * Exa.: key value caching, or caching of aggregations results
* <ins>Which caching design pattern is the most appropriate?</ins>

---

## Lazy Loading / Cache-Aside / Lazy Population 
* Pros
    * Only requested data is cached (the cache isn't filled up with unused data)
    * Node failures are not fata (just increased latency to warm the cache)
* Cons
    * Cache miss penalty that results in 3 round trips, noticeable delay for that request
    * Stale data: data can be updated in the database & outdated in the cache

### Topology
[<img src="https://i.imgur.com/ZcsrdZI.png">](https://i.imgur.com/ZcsrdZI.png)

### Python PseudoCode
````python
# Python

 def get_user(user_id):
     # Check the cache
     record = cache.get(user_id)
     
     if record is None:
        # Run a DB query
        record = db.query("Select * From Users Where id = ?", user_id)
        # Populate the cache
        cache.set(user_id, record)
        return record
      else:
        return record
        
 # App code
 user = get_user(17)
````

---

## Write Through - Add or Update cache when db is updated
* Pros
    * Data in cache is never stale, **reads are quick**
    * **Write penalty** vs Read penalty (each write requires 2 calls)
* Cons
    * Missing Data until it's added / updated in the DB. Mitigation is to implement Lazy Loading strategy as well
    * Cache churn - a lot of the data will never be read

### Toplogy
[<img src="https://i.imgur.com/Ov6b4OK.png">](https://i.imgur.com/Ov6b4OK.png)

### Python PseudoCode
````Python
# Python
def save_user(user_id, values):
  
  # Save to DB
  record = db.query("update users ... where id = ?", user_id, values)
  
  # Push into cache
  cache.set(user_id, record)
  return record
  
# App code
user = save_user(17, {"name":"Nate Dogg"})
```` 

---

## Cache Evictions & TTL
* Cache eviction can occur in **3 ways**:
    * You delete the item explicitly in the cache
    * Item is evicted because the memory is full & it's not recently used (LRU)
    * Yu set item TTL
* TTL are helpful for any kind of data:
    * Leaderboards
    * Comments
    * Activity streams
* TTL can range from few seconds to hours of days
* If too many evictions happen due to memory, you shold scale up or out

---

## Final words of wisdom
* Lazy Loading / Cache asside is easy to implement & works for many situations as a fundation, especially on the read side
* Write-through is usually conbined with Lazy Loading as targeted for the queries or workloads that benefit from this optimization
* Setting a TTL is usally not a bad idea, except when you're using Write-through. Set it to a sensible value for your application
* Only cache the data taht makes sense (user profiles, blogs, etc...)
* Quote: There are only 2 hard things in Computer Science: cache invalidation & naming things
