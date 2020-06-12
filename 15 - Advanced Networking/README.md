# VPC Flow Logs
## Key Points:
* Capture packet Metadata, not the content, not real time
* If interaction e.g. accepted&rejected - it's ACLs
* If SG, only one row(stateful)

* Never show up:
1. MetadataIP - 169.254.169.254 & 169.254.169.123
2. AWS DNS server
3. Amazon Windows License

# Egress-Only Internet Gateway
## Key Points:
* Oneway. Only inside out and response in. Outbound-only for IPv6.
* Architecture is same as Internet Gateway

# Vpc Endpoints 
## Gateway Endpoints
* Prefix add to route table
* Provide private S3 and DynamoDB
* Endpoint policy control what to access
* Regional & HA
* Security: S3 can be set to privately only except allowing from gateway endpoint

## Interface Endpoints
* Provide private access to AWS public services anything not S3 and DDB
* Not HA, add to specific subnets
* Can use SG control Endpoint Policies
* TCP&IPv4 only
* Use PrivateLink (Injecting to subnet)
* Endpoint provides a NEW service endpoint DNS
* Private DNS overides the default

## VPC Peering
* Direct encrypted network link between VPCs
* Same region
* No overlapping IPs
* VPC is not transitive, e.g. 3 VPCs need 3 peering router 4vpcs need 6
* Practical steps:
1. Create
2. Add to Route table
3. SG Inbound rules