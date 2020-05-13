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

 ## Internet Gateways IGW
 * 1 VPC has 0/1 IGW. 1 IGW belongs to 0/1 VPC