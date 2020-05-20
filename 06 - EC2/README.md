# EC2

# EBS
## Key Points:
* Storage Type
- SDD: gp2, io
- HDD: st1, sc1 | no boot volumn

* Volumns created&isolated in an AZ
* Snapshots help when AZ fail
* Generally 1 volume attach to one instance (Now have multi-attach)

# EC2 Instance Store Volume
* Attached at launch
* High Performance
* Local on EC2
* Lost on resize, move, hardware failure
* Price is included in instance price
* TEMPRORY

# Snapshot
* Increment bills&restore

# EBS Encryption
* Default EBS Encription can be enabled - default CMK or custom CMK
* Each volumes has 1 DEK (Data Encrytion Key)
* Snaps & future volums use the same DEK
* Can't remove Encrption on the current volumn 
* OS isn't aware of the encrytion - no performance loss
* If need OS/Full Disk Encrption or not aes256, don't use EBS Encryption

# Network Interface, IPs, and DNS
* Secondary ENI + MAC = Licensing
* Different Security Groups - multiple interfaces
* OS - Doesn't see public IPv4
* IPv4 Public IPs are Dynamic - Stop&Start = Change 
* Public DNS = private IP in VPC, Public IP everywhere else

# AMI
* AMI = One Region, only works in that one region
* AMI Baking - create an AMI + configuration
* An AMI can't be edited. Launch and update configuration and make a new AMI
* Can be copied between Regions
* Permission - default your account