# Hybrid Env and migration

# AWS Site to Site VPN
## Key Points:
* VPN runing on the public internet
* Full HA
* Quick & Less than an hour
* VGW, Virtual Private Gateway
* CGW, Customer Gateway
* VPN Connection between VGW and CGW
* AWS speed limit 1.25Gbps
* Inconsistent because public internet
* Dynamic IP will need BGP protocol
* Quick setup

# AWS Direct Connect DX
* DX takes much longer to provision vs VPN - weeks/months
* Faster 40Gbps with Aggregation
* Low latency & consistent
* Don't use business bandwidth
* NO ENCRYPTION

# Transit Gateway
* Improve the mesh (VPN Peering design)
* Single TGW transit all vpcs
* Much simpler structure
* Practical: 
1. Create TGW
2. TGW attachment
3. VPC route table add other vpcip with Target TGW

# Storage Gateway
* Migration, Extention, Backup
* 3 Modes:
1. Tape Gateway VTL Mode => S3 Glacier
2. File Mode SMB and NFS => S3
3. Block storage backed by S3 & EBS Snapshot
  3.1 Volumn(Stroge Mode) => localblocks and s3 async backup
  3.2 Volumn(Cached Mode) => upload to s3 and cache frequent data
* Difference between file&volumn storage is FILES and BLOCKS(VOLUMN)

#