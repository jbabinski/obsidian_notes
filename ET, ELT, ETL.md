Batch pipelines -  pipelines that process a bounded amount of data and then exit.
![[Pasted image 20230329135413.png]]
ELT/ETL - ETL transforms data whenever its needed, after it is loaded. ETL uses intermediate process of transforming the data before it's loaded.

![[Pasted image 20230329135715.png]]
![[Pasted image 20230329135738.png]]

##### Quality considerations
![[Pasted image 20230329140218.png]]

BQ can be used to filter the data before being stored in target table.

##### Shortcomings/ETL
- when you cannot transform data using SQL, you need to use ETL 
![[Pasted image 20230329140850.png]]
![[Pasted image 20230329141324.png]]
Other products:
[[DataProc]]
[[Cloud Data Fusion]]

**Lineage** - metadata about the data
**Labels** - are used to track lineage. key, value pair. Can be used to track billings.

[[Data Catalog]]