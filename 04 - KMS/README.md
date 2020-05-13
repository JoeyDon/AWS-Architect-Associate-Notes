# KMS

## Key Points:
* Align with US FIPS 140-2(L2)
* CMKs can be used for up to 4kb data
* CMKs spcific to a region & keys never leave KMS
* CMKs supports rotations
* CMKs key has Aliases for application
* Key policies. One account ARN as a priciple(Trust). IAM has permission to key & key policies refers back to IAM ARN
* DEK(Data Encryption Key) > 4kbs. 
* Multipart upload -> (file > 100gb) & 10000 max parts & 5mb->5gb & parts can be failed and restarted