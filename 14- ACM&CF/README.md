# ACM
## Key Points:
* With CF, cert has to be created in us-east-1
* Supports: EC2, CF
* ACM needs to be in same region
* Process:
1. Register Domain
2. ACM Validate SSL with Domain via Email/DNS
3. Create record in Route 53
4. CloudFront Distribution - Add domain as CNAME
5. Import Custom SSL from ACM
6. Route 53 add domain with targeting alias with Cloudfront

# Secure CF&S3
* OAI Origin Access Identity
* Bucket policy implicitly deny - only trust OAI

# Compared to GA - Global Accelerator
* GA reduces hops, data transit with AWS backbone network
* GA support TCP/UDP
* CF distribute caches
