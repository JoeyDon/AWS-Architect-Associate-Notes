# DynamoDB (DBaaS)
* Across AZs and global
* Encrytion at rest
* Event-driven support
* Point-in-time Recovery(PITR)
* Billed based RCU, WCU, Storage and Features
* Scan always consumes all capacity then discard 

* Strong Consistent and Eventual Consistent
- Strong Consistent may read unupdated data from other AZs 

* WCU is n/1
* RCU is n/4

* Stream
- Per table
- Records Inserts, Updates, Deletes
KEYS_ONLY
NEW_IMAGE
OLD_IMAGE
NEW_AND_OLD_IMAGES

* Triggers (Lambda)
- Aggregation, Messaging, Notifications

* LSI (Local Secondary Indexes)
- Must create with table
- Maximum 5

* GSI (Global Secondary Indexes)
- Created any time
- Max 20

* LSI and GSI Considertations
- Careful with projection(KEYS_only,INCLUDE,ALL)

* DynamoDB - Accelerator (DAX)
1. DAX Sdk from application
2. Less complexity for App Dev
3. DAX creates RR in other AZs

* Amazon Athena
1. Pay only data consumed
2. Schema-on-read
3. Works with data structured, semi-, or un-structured in S3