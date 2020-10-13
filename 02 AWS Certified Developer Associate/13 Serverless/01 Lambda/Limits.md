# Limits

## Acronym

## Doc

## Limits to knwo - per region
* Execution:
    * Memory allocation: 128MB - 3008MB (64 MB increments)
    * Maximum execution time: 900s (15 minutes)
    * Env variable (4KB)
    * Disk capacity in the "function container" (in/tmp): 512 MB
    * Concurrency execution: 1000 (can be increased)
* Deployment:
    * Lambda function deployment size (compressed .zip): 50 MB
    * Size of uncompressed deployment (code + dependencies): 250 MB
    * Can use the /tmp directory to load other files at startup
    * Size of env vairables: 4 KB
