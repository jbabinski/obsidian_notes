![[Pasted image 20230319194818.png]]
- object store
- buckets - containers for objects, unique namespace, assosiated with region(s) 
- objects
	- exist in buckets:
	- torage replicates it to increase its durability, for multiple regions between regions, if it's single-region, then between zones
	- retrieved from the closest replica for low latency
	- stored with metadata
- different classes:
	- Standard Storage - best for frequently accessed data, brief period of time
	- Nearline Storage - for infrequently used data (1xM or less) - like archive, backups
	- Coldline Storage - for data accessed once per 3M
	- Archive Storage - once a Y, e.g. Disaster Recovery files
- Cloud Storage simulated a file system:
![[Pasted image 20230319195728.png]]
- object management features:
	- retention policy
	- versioning
	- lifecycle management

##### Secure Cloud Storage
- two separate methods:
	- [[IAM]]
	- ACL - access control level. Can be set on a bucket level or object level
- data encryption:
	- Google-managed encryption keys (GMEK) - automatic
	- Customer-managed encryption keys (CMEK) - user-controlled KEK key in Cloud KMS
	- Customer-supplied encryption keys - user provides KEK key
![[Pasted image 20230319200529.png]]
- special cases:
![[Pasted image 20230319200805.png]]

##### Storing different data types
![[Pasted image 20230319201133.png]]
[[Data lakes and data warehouse#Transactional databases versus data warehouses]]
[[Cloud SQL]] - for single database, one geographical region
[[Cloud Spanner]] - better for multiple applications across the globe

[Online analytical processing (OLAP) vs. online transactional processing (OLTP)](https://www.ibm.com/cloud/blog/olap-vs-oltp)

##### Cloud Storage instead of HDFS
-  due to slow internet speed, HDFS computed and stored data  
![[Pasted image 20230408205644.png]]
- you can put your HDFS jobs on DataProc without significant changes
- petabit bandwidth allows processing data where it is without copying it
- Collosus - storage layer within Google data center
- Jupyter - network inside the data center
![[Pasted image 20230408210222.png]]
![[Pasted image 20230408210421.png]]
- disadvantages of CS vs. HDFS - renaming objects or directories