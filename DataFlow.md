- DataFlow creates pipeline for both batch and streaming data
- Extract, Transform, Load data (ETLC)
- Serverless - resource provisioning, performance tuning & pipeline reliability managed on behalf of the users
- NoOps - automated Maintenance, Monitoring & Scaling
- designed to be low-maintenance
- user don't have to mointor all storage and compute resources - templates can be used

Dataflow processes:
1. Graph optimization - remove inefficiencies
2. Work scheduler - schedules work among workers
3. Auto-scaler - scales no of workers used
4. Auto-healing - heals worker flaws
5. Work rebalancing - rebalance work to effectively use workers
6. Compute & storage - save output

![[Pasted image 20230307120040.png]]

Dataflow templates + examples:
- streaming
![[Pasted image 20230307120253.png]]
- batch
  ![[Pasted image 20230307120313.png]]
- utility
![[Pasted image 20230307120356.png]]

##### Run batch processing pipelines
Introduction

Dataflow vs. Dataproc
![[Pasted image 20230518120935.png]]
![[Pasted image 20230518121116.png]]
- Dataflow is recommended for new pipelines
- DF is scalable and has low latency

![[Pasted image 20230518121323.png]]

[[Apache Beam#Batch+strEAM]]

![[Pasted image 20230518122350.png]]
- DF is fully-managed and auto-configured
- DF optimizes Apache Beam graphs
- auto-scales in the middle of the job

##### Pipelines in code

- simple pipeline:
![[Pasted image 20230518123228.png]]

- branching:
![[Pasted image 20230518123305.png]]

1. Create a pipeline
![[Pasted image 20230518123610.png]]
2. Run pipeline on DF
![[Pasted image 20230518123638.png]]
3. Execute pipeline using DataflowRunner
![[Pasted image 20230518123716.png]]

##### Key considerations with designing pipelines
![[Pasted image 20230518123910.png]]

![[Pasted image 20230518124007.png]]

![[Pasted image 20230518124044.png]]


##### Transforming data with PTransforms
![[Pasted image 20230518124330.png]]
![[Pasted image 20230518124441.png]]
![[Pasted image 20230518124606.png]]

##### Aggregate with GroupByKey and Combine
Map (group) -> Reduce

![[Pasted image 20230518133300.png]]
- skewed data - when workloads between 2 grouping jobs is significantly different
![[Pasted image 20230518133445.png]]

![[Pasted image 20230518133641.png]]

![[Pasted image 20230518133746.png]]

- Combine is way faster than GroupBy - it can be pararellized
![[Pasted image 20230518133854.png]]

##### Side inputs and Windows of data
- global windows
- time-based windows

![[Pasted image 20230518135919.png]]

- bounded PCollection & global window
![[Pasted image 20230518140414.png]]

- unbounded PCollection and global window :(
![[Pasted image 20230518140510.png]]

- time-based windows & time-series data
![[Pasted image 20230518140634.png]]

- batch & group by time
![[Pasted image 20230518140703.png]]

##### Creating and re-using Pipeline Templates
![[Pasted image 20230518160430.png]]
![[Pasted image 20230518160517.png]]

##### Streaming features
![[Pasted image 20231027221905.png]]
![[Pasted image 20231027221952.png]]
![[Pasted image 20231027222043.png]]
![[Pasted image 20231027222116.png]]
![[Pasted image 20231027222135.png]]
![[Pasted image 20231027222219.png]]
- replacing timestamp to when system sent the message instead of receiving the message
![[Pasted image 20231027222346.png]]
![[Pasted image 20231027222356.png]]
![[Pasted image 20231027222418.png]]

##### Windowing
![[Pasted image 20231027223011.png]]
![[Pasted image 20231027223049.png]]
![[Pasted image 20231027223118.png]]
![[Pasted image 20231027234831.png]]
![[Pasted image 20231027234912.png]]
- watermark
![[Pasted image 20231027234939.png]]
![[Pasted image 20231027235023.png]]
- what happens to late data? it's configurable
![[Pasted image 20231027235710.png]]
![[Pasted image 20231027235907.png]]
![[Pasted image 20231027235958.png]]
![[Pasted image 20231028000055.png]]
