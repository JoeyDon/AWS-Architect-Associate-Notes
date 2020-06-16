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

# Snowball
1. 10TB to 10PB multiple devices
2. Multiple devices to multiple premises
3. Only STORAGE

# Snowball Edge
1. Both storage and compute
2. faster internet
3. larger capacity

# Snowmobile
1. Portable DC on a truck
2. Up to 100PB
3. Drive to your location
4. Single&One truck (One site) e.g. not suitable for 1PB but 5 sites

# AWS Directory Service
* AWS managed
* Some services need a directory e.g Amazon Workplace
* Or act as a proxy
* 3 modes 
1. Simple AD - direct SAMBA
2. AWS managed Microsoft AD connect by VPN
3. AD Connector - on-premises directory proxy 

# AWS DataSync
* Designed to work at huge scale
* Keeps metadata
* Built in data validation
* Scalable
* Compression and encrytion
* Auto-recovery
* Pay as you use
* Bandwidth throttling
* Scheduled
* Integrate with S3, EFS(Elastic File System), FSx (For windows)
* Task - a job 
* Agent - Software used to read or write using NFS or SMB
* Location - NFS(Network File System), Server Message Block(SMB), Amazon EFS, Amazon Fsx and S3
* Key words:
1. Can be scheduled
2. Amazon FSx (Windows)
3. Huge scale with metadata

# FSx
* Native windows file servers
* Integration with Windows Env
* On-demand&Scheduled Backups
* Access by VPN, Peering, VPN, Direct Connection
* EFS is linux <=> FSx is for windows
* Using SMB copy
* Shadow copies
* Key words
1. VSS User-driven restores
2. Native file system over SMB
3. Windows Permission Model
4. Support DFS. Distributed File System.
5. Managed - no file server admin
6. Integrates with DS and your own directory

# AWS Secrects Manager
* Directly integrets AWS products(...RDs)
* Password rotations(by a Lambda)