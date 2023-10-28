- SQL
- analytical workload

BQ features:
- Storage + analytics
- Serverless data warehouse
- Flexible pay-as-you go pricing model
- Data encrtyption at rest (for data stored on a disk)
- Built-in ML

##### Storage and analytics
![[Pasted image 20230308101155.png]]

Can utilize external data sources
![[Pasted image 20230308101402.png]]

Loading data to BQ
![[Pasted image 20230308101646.png]]

BQ Analytics
![[Pasted image 20230308101748.png]]
![[Pasted image 20230308101819.png]]

##### Machine Learning
ML models can be creted using SQL queries
![[Pasted image 20230308110326.png]]
![[Pasted image 20230308110351.png]]
Hyperparameters (e.g. train/test split rate) can be set by user or defaults can be used
BQ supports both supervised and unsupervised models
![[Pasted image 20230308110623.png]]
![[Pasted image 20230308110641.png]]

##### ML project phases & ML Commands

![[Pasted image 20230308113044.png]]

CREATE MODEL
![[Pasted image 20230308115728.png]]
ML.WEIGHTS
![[Pasted image 20230308115806.png]]
- result is list of reatures ranked -1 to 1 depending on their effect on Y ( 0 - unimportant, +1 - positive correlation, -1 - negative corr)

ML.EVALUATE
![[Pasted image 20230308115957.png]]

ML.PREDICT
![[Pasted image 20230308120022.png]]

Supervised models
![[Pasted image 20230308120239.png]]

Unsupervised models

##### BigQuery as Data Warehouse
![[Pasted image 20230318113806.png]]

![[Pasted image 20230327204056.png]]

- BQ is column-oriented, making it faster than relational dbs (row-oriented)
- BQ is OLAP system and is not optimized to updates but to reads
- Storage Engine and Analytic Engine
![[Pasted image 20230327204337.png]]
- BQ's distributed file system -> Colossus
- BQ slots - combination of CPU, memoty and networking resources
	- 2000 slots of on-demand slots

##### Get started with BQ
- data organized into datasets
- project.dataset.table
- billing related to a project
- requires access to querierying project in [[IAM]] 
- datasets can be regional or multi-regional
- tables' schemas - provided manually or via JSON file
- row-level policies are possible to set up
- user can create authorized view without granting access to underlying data
- materialized view - view is not queried every time a view is used
- materialized view updates when new data is available in underlying tables
- cost of storage and queries can be separated

##### Load data into BQ
**Extract and Load:** 
- Big Query Data Transfer
- Big Query
	Batch loads:
	![[Pasted image 20230327210018.png]]
	- limits for number and file size of loads
- Cloud Storage
- BQ supports disaster recovery queries:
	![[Pasted image 20230327210308.png]]

	**BQ Data Service** 
	- provides SaaS (software as a sevice connectors)
	- can transfer data between regions or from software without Cloud Storage buckets
- Extract, Load, Transform
	- Big Query - load data from CS and then transform via sql to create data warehouse
	- user can create UDFs and share them locally/publically

##### Streaming
![[Pasted image 20231028141625.png]]
![[Pasted image 20231028141852.png]]
BI Engine
![[Pasted image 20231028142446.png]]

##### Window & GIS functions
![[Pasted image 20231028155209.png]]
![[Pasted image 20231028155221.png]]
GIS - geographic information system
![[Pasted image 20231028155329.png]]
![[Pasted image 20231028155346.png]]
![[Pasted image 20231028155429.png]]
![[Pasted image 20231028155502.png]]
![[Pasted image 20231028155513.png]]
![[Pasted image 20231028155534.png]]
##### Performance optimization
![[Pasted image 20231028155814.png]]
![[Pasted image 20231028155905.png]]
![[Pasted image 20231028160010.png]]
![[Pasted image 20231028160126.png]]
![[Pasted image 20231028160737.png]]![[Pasted image 20231028160810.png]]
![[Pasted image 20231028160834.png]]
![[Pasted image 20231028160903.png]]
![[Pasted image 20231028160939.png]]
![[Pasted image 20231028160950.png]]
![[Pasted image 20231028161003.png]]
![[Pasted image 20231028161020.png]]

#### Cost consideration
![[Pasted image 20231028163716.png]]
![[Pasted image 20231028163818.png]]
![[Pasted image 20231028163832.png]]
![[Pasted image 20231028163845.png]]
![[Pasted image 20231028163858.png]]
![[Pasted image 20231028164338.png]]
![[Pasted image 20231028164430.png]]
![[Pasted image 20231028164532.png]]
![[Pasted image 20231028164613.png]]
