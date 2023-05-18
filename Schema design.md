- normalizing the data -> turning the data into relational system
- organizes the data, takes less space
- data warehouses often denormalizes -> e.g. repeats data to increase read performance
- some denormalazation processes can slower data processing - like one-to-many relation
- BQ solves this problem by using nested and repeated data

##### Nested and repeated fields
- normalized data - JOINs are costly
- denormalized data - data repeated
- nested and repeated fields allows to have different levels of granularity
- STRUCTS (RECORD)
- ARRAYS (REPEATED) - can be part of regular fields or structs

##### Optimize with partitioning and clustering
- partitined table is chaper to query -> it reduces data to be read
- partitioning types:
	- ingestion time
	- any column that is DATETIME, DATE, TIMESTAMP
	- integer-type column
- BQ sorts the data based on values in the clustering columns
- clustering set up at table creation time
- data is reclustered from time to time
![[Pasted image 20230327220209.png]]