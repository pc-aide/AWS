# S3

## Acronym
* S3 - Simple Storage Service

## Doc

## Introduction
* I'ts advertised as "infinitely scaling" storage
* Many websites usue S3 as a backbone

---

## Buckets
* S3 allows people to store objects (files) in "buckets" (directories)
* Buckets must have a globally **unique name**
* Buckets are defined at the region level
* Naming covention
    * No uppercase
    * No underscore
    * 3-63 characters long
    * Not an IP
    * Must start with lowercase letter or number
    
### Objetcts
* Objects (files) have a key
* The **key** is the **full** path:
    * s3://my-bucket/**my_file.txt**
    * s3://my-bucket/**my_folder1/another_folder/my_file.txt**
* The key is composed of **prefix** + **object name**
    * my_folder1/another_folder - prefix
    * my_file.txt - object name
* There's no concept of "directories" within buckets (although the UI will trick you to think otherwise)
* Just keys with very long names that contain slashes ("/")
* Object values are the content of the body:
    * Max Object Size is 5 TB 
    * If uploading more than 5 GB, must use "multi-part upload"
* Metadata (list of text key / value paris - system or user metadata)
* Tags (Unicode key / value pari - up to 10) - useful for security / lifecycle
* Version ID (if versioning is enabled)
