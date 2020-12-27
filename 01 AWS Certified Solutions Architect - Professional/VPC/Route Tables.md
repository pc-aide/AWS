# Route Tables

## Abbreviation
* igw - Internet Gateway

## Intro
* Main or custom table
* Table type
  * Subnet
  * Gateway
    * Internet Gateway
    * Private Gateway
  * Local gateway
* One route table per subnet
* Each subnet has a router at +1 (address)

---

## Main & Custom Tables
* Main generated during VPC creation
* Implicit or explicit association
* Main designation can be changed
* Leave main empty
  * Except local routes
* Custom uses explicit association

---

## Route
* e.g.
  * rtb-default:
  * igw-default

|Destination  |Target      |Status|Propagated|
|-------------|------------|------|----------|
|172.31.0.0/16|local       |active|No        |
|0.0.0.0/0    |igw-2bea2c43|active|No        |
