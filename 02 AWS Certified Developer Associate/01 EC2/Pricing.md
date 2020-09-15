# Pricing

## Doc
* [On-demand](https://aws.amazon.com/ec2/pricing/on-demand)

## EC2 Pricing
* EC2 instances prices (per hour) varies based on thes parameters
    * Region
    * Instance Type (t2.micro, t2.medium, etc)
    * On-Deman vs Sport vs Reserved vs Dedicated Host
    * OS (Linux or Windows, RHEL for examples)
* You are billed by the second, with a minimum of 60 seconds
* You also pay for others factors
    * Storage
    * Data transfer
    * Fixed IP public addresses
    * Load balancing
* You do not pay for the instance if the instance is stopped

### E.g
* t2.small in us-east-1a (Virginia), Cost $0.023 per hour
* If used for
    * 6 seconds, it costs $0.023/60 = $0.000383333333 (minimum of 60 seconds)
    * 60 seconds, it costs $0.023/60 = $0.000383 (minimum of 60 seconds)
    * 30 minutes, it costs $0.023/2 = $0.0115
    * 1 month, it costs $0.023*24*30 = $16.56 (assuming a month is 30 days)
    * X seconds (x > 60), it costs $0.023 * x / 3600
