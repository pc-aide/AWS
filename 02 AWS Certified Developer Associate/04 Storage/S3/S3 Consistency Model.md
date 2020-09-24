# S3 Consistency Model

## Acronym

## Terminology
* 200 = ok (HTTP methods)
* 404 - for not existing

## Doc

## Intro
* Read after write consistency for PUTS of new objects
    * As soon as new object is written, we can retrieve it 
      * ex: PUT 200 => GET 200
    * This is true, **except** if we did a GET before to see if the object existed
      * GET 404 => PUT 200 => GET 404 - eventually consistent
* Eventual Consistency for **DELETES** & **PUTS** of existing objects
    * If we read an object after updating, we might get the older version
      * ex: PUT 200 => PUT 200 => GET 200 (might be older version)
    * If we delete an object, we might still be able to retrieve it for a short time
      * ex: DELETE 200 => GET 200
* Note: there's no way to request "strong consistency"
