# Application Discovery Service

## Acronym
* OVA - Open Virtual Applicance

## Limit
* Not available : ca-central [02-02-2021]

## Intro
* Plan migration projects by gathering information about on-premises data centers
* Server utilization data & dependency mapping are important for migrations
1. **Agentless discovery** (Application Discovery Agentless Connector):
   * OVA package that can be deployed to a VMware host
   * VM inventory, configuration, & performance history such as CPU, memory, & disk usage
   * OS agnostic  
2. **Agent-based discovery**:
   * system configuration, system performance, running processes, & details of the network connections between systems
   * Supports Microsoft Server, Amazon Linux, Ubuntu, RedHat, CentOS, SUSE...
* Resulting data can be exported as CSV or viewed within AWS Migration Hub
* Data can be explorer using pre-fefined queries in Amazon Athena
