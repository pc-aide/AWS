# Route Tables

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
