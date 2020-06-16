# AWS Secrects Manager
* Directly integrets AWS products(...RDs)
* Password rotations(by a Lambda)

# AWS Shield
* DDos Protection
1. Shield Standard - free with Route 53 and Cloudfront
- Protection against Layer 3 and Layer 4
2. Shield Advanceds $3,000 / Month
- EC2, ELB, CloudFront, Global Accelerator, R53
- DDoS response team and finicial insurance

# AWS WAF
* Layer 7(http/s) Firewall
* SQL Injections, Cross-site scripting.
* WEBACL integrated with ALB, API Gateway and Cloudfront

# CloudHSM (Without AWS API integration)
* HSM - Hardware Security Module
* AWS provisioned
* Fully FIPS 140-2 Level 3 <=> KMS is L2
* Interact with PCKS#11, JAVA JCE, Ms CryptoNG libraries
* AWS can't access keys
## Use cases
* No native AWS integration e.g. no S3, SSE
* Offload the SSL/TlS processiong for Web Servers
* Eable Transparent Data Encrytion(TDE) for Oracle DBs
* Protect the private key for issuing Certificate Authority(CA)