# SSM Hybrid Environment

## Table
| AWS EC2                                 | On-Premises Servers/VMs                                              |
| --------------------------------------- | -------------------------------------------------------------------- |
| SSM agent usually installed by default  | SSM agent NOT installed by default                                   |
| Enable & start the SSM Agent            | Must install AWS provided TLS cert                                   |
| Allow interaction with SSM via IAM role | Create managed-instance activation<br>& receive activation ID & code |
|                                         | Install the SSM Agent, then configure<br>with activation code & ID   |
