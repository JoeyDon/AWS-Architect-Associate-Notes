# VPC

## Key Points:
* One subnet has to be in one AZ
* One AZ can have many subnets
* A subnet cannot be overlapping with others 
* 5 reserved in every subnet. e.g. in 10.16.0.0/20 (10.16.16.0 ~ 10.16.31.255)
 - 10.16.16.0 Network address
 - 10.16.16.1 VPC Router
 - 10.16.16.2 Reserved (DNS)
 - 10.16.16.3 Reserved Future Use
 - 10.16.31.255 Boardcast in subnet
* valid sizes - max /16 . min /28
 ## Internet Gateways IGW
 * 1 VPC has 0/1 IGW. 1 IGW belongs to 0/1 VPC

 ## NACL - Network Access Control List
 * Stateless - Initiation and Response are different(Inbound and Outbound)
 * Only impacts data acrossing subnets
 * Can explicityly deny or allow
 * No logical resources
 * NACL only supports subnets (No ec2 or other single resource)
 * One subnet => One NACL  

 # SG - Security Group
 * Stateful - Traffic and Response are treated as same. Auto-allow response.
 * SGs can filter logical resources. (NACL only IP)
 * Implicity deny and explicitly allow
 * No explicit deny

 # SG vs NACL
 * NACLs on subnet for any products which dont work with SG(NAT Gateway)
 * NACLs for explitly deny.
 * SG as default for anything else

 # NAT Gateway
 * Runs from a public network
 * Uses Elastic IPs
 * AZ Resilient Services 
 * Up to 45Gbps
 * Charged on 1.Hourly charge, 2. Data transmitted
 * Only with NACL because no Instance. Nor portforwading and bastion
 * Alternative to NAT Instance
 * NAT Gateway doesn't work with IPv6