# Function Performance

## Doc

## Acronym
* DB - Database

## Lambda Function Configuration
* RAM:
    * From 128MB to 3.008MB in 64MB increments
    * The more RAM you add, the more vCPU credits you get
    * At 1.792MB, a function has the equivalent of one full vCPU
    * After 1.792MB, you get more than one CPU, & need to use multi-threading in your code to benefit from it
* **If you application is CPU-bound (computation heavy), increase RAM**
* **Timeout**: default 3 seconds, mazimum is 900s (15 minutes)

---

## Lambda Execution Context
* The execution context is a temporary runtime environment that initializes any external dependencies of your 
  lambda code
* Great for db connections, HTTP clients, SDK clients...
* The execution contet ins maintained for some time in anticipation of another Lambda function invocation
* The next function invocation can "re-use" the context to execution time & save time in initializing connections
  objects
