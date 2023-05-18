https://www.coursera.org/learn/gcp-big-data-ml-fundamentals/lecture/AaHYF/storage

Compute and storage are decoupled - processing limitations aren't attached to storage disks.

- [[Cloud Storage]]
- [[Cloud BigTable]]
- [[Cloud SQL]]
- [[Cloud Spanner]]
- [[Firestore]]
- [[BigQuery]]

Solution to be selected based on data type and business needs
Data types:
- Unstructured (Documents, Images, Audio)
- Structured (stored in tables with rows and columns)

Data stored in Buckets
Each Project - Bucket - Object is a resource in GC

Cloud Storage classes:
- Standard Storage - best for frequently accessed data, brief period of time
- Nearline Storage - for infrequently used data (1xM or less) - like archive, backups
- Coldline Storage - for data accessed once per 3M
- Archive Storage - once a Y, e.g. Disaster Recovery files

Structured Data solutions:
![[Pasted image 20230307093750.png]]
Transactional workload - affects a few records
Analytical workload - requires more complex tools, access to whole datasets
[transactional vs analytical workload](https://medium.com/@guxie/data-engineering-transactional-vs-analytical-workloads-ab1a03832b2c)