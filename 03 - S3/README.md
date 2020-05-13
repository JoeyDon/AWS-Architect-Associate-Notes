# IAM S3

## Key Points:
* Unlimited data size in any bucket
* Data stored as object
* Version control can be only suspended but not disabled, if it's enabled
* Multipart upload -> (file > 100gb) & 10000 max parts & 5mb->5gb & parts can be failed and restarted

## Encryption:
* Client-Side Encryption
* SSE-C (Customer manage key, s3 en/decrypt)
* SSE-S3 (s3 manage key / unique for each object), default & aes-256
* SSE-KMS
* By default, header => AES256 or aws:kms. If bucket policies don't specify anything.

## Storage:
* S3 Standard. Duplicate across 3AZs
* S3 Standard - IA. 
    - Minimum 128kb charged, 
    - 30 days minimum charge, 
    - per GB minimum rotations
    - 50% cheaper than S3 standard
* S3 One Zone - IA. 
    - One AZ. 
    - 20% cheaper than S3 Standard - IA. 
    - Can't stand AZ failure
* S3 Glacier - 
    - 17% cost of S3 Standard. 
    - 11 9's Durability, 4 9's Availability, 3+ AZ replications. 
    - No immediate request.
    - Minimum 40kb charged,
    - 90 days minimum charge, 
* S3 Glacier Deep Archive - 
    - 4% Cost of S3 standard
    - 180 days minimum charged,
    - Retrival in 12 hours,
    - Can't make data public / download normally

## Replication
* Not retroactive - from now on. 
* One way source to destination
* Both version control needs to be on
* Unencryed and SSE-s3 and SSE-KMS(extra config)
* Source bucket owner needs permisson to objects
* No system events(lifecyle) copy over. 
* No Glacier&Glacier Deep Archive
* Deletes are not replicated

## Presigned URL
* Permission is the same as the identity gives the presigned URLs
* Don't generate a role, if temp credential is expired, url will stop working.