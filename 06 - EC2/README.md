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

# EC2 Pricing
* On Demand
* Spot Price(Off-peak) - fail tolerant 70%off roughly
* Reserved 1 or 3 years - 75% off

# EC2 Metadata
* Address 169.254.169.254/latest/meta-data
* Default not encrpted - unless firewall blocks

# Userdata
* 169.254.169.254/latest/user-data
* Excuted on launch only.
* Cfn:init in Userdata will triger on every updates
* Cfn:signal returns the excusion result
* EC2 doesn't intrepret data, OS needs to understand
* Not secure. 
* 16kb maximum. Oversize will need to pass a script and download the data.
* Optimal: 1. EC2 baked AMI + Userdata(Boorstraping)
* Optimal: 2. EC2 yaml including the base64 decoded userdata

# EC2 Instance Roles
* Only the InstanceProfile is attached to an instance
* Roles is better than storing pair-keys in EC2

# Parameter Store
* String, String List, Secured String (KMS with spcific key)

# EC2 Logging / Logs
* Use Cloudwatch Agent. 
* Best way is using Roles on EC2 to do permissions.
* CLI : Install CWAgent => AgentConfigWizard => Config different log groups => Save to ParameterStore => Load from parameterStore => Start CWAgent

# EC2 Placement Group
* low latency, stream 5g to 10g. 
* One AZ - One fail all fail
* Can span VPC peers