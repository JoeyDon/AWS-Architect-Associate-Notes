# RDS

## Key Points:
* Can be Multi AZ by Syncchronous MultiAZ
- RDS access via CNAME
- CNAME auto failover to AZ-B instance 
- Standby can't be used
- Same region only
- Backup taken from Standby

* Asyncly read-replicas
- 5x direct read-replicas per DB instance
- Read-replica can have read-replica - but lags
- Global performane improvements
- Snapshots&Backups improve PRO
- RTO still a problem
- Global availibility improvements with global resilience
- Read only until promoted - not reversable

* Backups
- RTO vs RPO
- Recovery Point Object: Time between last backup to incident
- Recovery Time Object: Time between incident to recover

* RDS Restores
- Create a new RDS Instance - new address
- Snapshops = single point in time
- Automated = any 5 minute point in time 
- Backup is from restored snapshots then 'replay' use transactions logs
- Restores aren't fast - think about rto

* Sync VS Async
- Sync : MultiAZ
- Async : Read-replica