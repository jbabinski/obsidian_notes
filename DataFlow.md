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

##### Beam Portability

![[Pasted image 20231126202714.png]]
![[Pasted image 20231126202744.png]]

![[Pasted image 20231126202825.png]]
![[Pasted image 20231126202850.png]]
![[Pasted image 20231126202952.png]]
![[Pasted image 20231126203033.png]]
![[Pasted image 20231126204057.png]]
![[Pasted image 20231126204200.png]]
![[Pasted image 20231126204227.png]]
![[Pasted image 20231126204327.png]]
![[Pasted image 20231126204340.png]]![[Pasted image 20231126204518.png]]
![[Pasted image 20231126204528.png]]
![[Pasted image 20231126204613.png]]

##### Separating Compute and Storage with Dataflow
![[Pasted image 20231126204836.png]]
![[Pasted image 20231126204942.png]]
![[Pasted image 20231126205051.png]]
![[Pasted image 20231126205107.png]]
![[Pasted image 20231126205213.png]]
![[Pasted image 20231126205310.png]]

##### IAM, Quotas and Permissions
![[Pasted image 20231126212549.png]]
![[Pasted image 20231126212602.png]]
![[Pasted image 20231126212757.png]]
![[Pasted image 20231126212723.png]]
![[Pasted image 20231126212808.png]]
![[Pasted image 20231126212907.png]]
![[Pasted image 20231126212929.png]]
![[Pasted image 20231126213042.png]]

##### Quotas
![[Pasted image 20231126213143.png]]
![[Pasted image 20231126213254.png]]
![[Pasted image 20231126213402.png]]
![[Pasted image 20231126213439.png]]
![[Pasted image 20231126213559.png]]
![[Pasted image 20231126213652.png]]
![[Pasted image 20231126213745.png]]
##### Security
![[Pasted image 20231126214528.png]]
![[Pasted image 20231126214628.png]]
![[Pasted image 20231126214643.png]]
![[Pasted image 20231126214657.png]]
![[Pasted image 20231126214713.png]]![[Pasted image 20231126214908.png]]
![[Pasted image 20231126214928.png]]
![[Pasted image 20231126215105.png]]
![[Pasted image 20231126215114.png]]

![[Pasted image 20231126215303.png]]
![[Pasted image 20231126215311.png]]

##### Beam Concepts Review
![[Pasted image 20231202143833.png]]
![[Pasted image 20231202144231.png]]
DOCZYTAĆ
![[Pasted image 20231202144335.png]]
![[Pasted image 20231202144425.png]]
![[Pasted image 20231202144608.png]]
https://beam.apache.org/documentation/transforms/python/overview/
https://beam.apache.org/documentation/basics/
https://beam.apache.org/documentation/programming-guide/
https://beam.apache.org/documentation/patterns/overview/

##### Windows, watermarks, triggers
![[Pasted image 20231225133721.png]]
![[Pasted image 20231225133734.png]]
![[Pasted image 20231225133856.png]]![[Pasted image 20231225133929.png]]
![[Pasted image 20231225133939.png]]
![[Pasted image 20231225134015.png]]
![[Pasted image 20231225134152.png]]
![[Pasted image 20231225134352.png]]
![[Pasted image 20231225134405.png]]
![[Pasted image 20231225134426.png]]
![[Pasted image 20231225134505.png]]
![[Pasted image 20231225134641.png]]
![[Pasted image 20231225134813.png]]
![[Pasted image 20231225134855.png]]
![[Pasted image 20231225135119.png]]
![[Pasted image 20231225135413.png]]
![[Pasted image 20231225135435.png]]
![[Pasted image 20231225135515.png]]
![[Pasted image 20231225135618.png]]
![[Pasted image 20231225135641.png]]
![[Pasted image 20231225135731.png]]
![[Pasted image 20231225135810.png]]
![[Pasted image 20231225135916.png]]

##### Sources and sinks
![[Pasted image 20231225212108.png]]
![[Pasted image 20231225212130.png]]
![[Pasted image 20231225212140.png]]
![[Pasted image 20231225212227.png]]
![[Pasted image 20231225212253.png]]
![[Pasted image 20231225212311.png]]
https://beam.apache.org/documentation/io/connectors/

![[Pasted image 20231225212446.png]]
![[Pasted image 20231225212538.png]]
![[Pasted image 20231225212616.png]]
![[Pasted image 20231225212711.png]]
![[Pasted image 20231225212730.png]]
![[Pasted image 20231225212824.png]]
![[Pasted image 20231225212848.png]]
![[Pasted image 20231225212858.png]]
![[Pasted image 20231225212928.png]]
![[Pasted image 20231225213009.png]]
![[Pasted image 20231225213051.png]]
![[Pasted image 20231225213125.png]]
![[Pasted image 20231225213143.png]]
![[Pasted image 20231225213216.png]]
![[Pasted image 20231225213238.png]]
![[Pasted image 20231225213320.png]]
![[Pasted image 20231225213341.png]]
![[Pasted image 20231225213410.png]]
![[Pasted image 20231225213419.png]]
![[Pasted image 20231225213443.png]]
![[Pasted image 20231225213521.png]]
![[Pasted image 20231225213531.png]]
![[Pasted image 20231225213611.png]]

##### Schemas
![[Pasted image 20231225221915.png]]
![[Pasted image 20231225222010.png]]
![[Pasted image 20231225222035.png]]
![[Pasted image 20231225222125.png]]
![[Pasted image 20231225222200.png]]

##### State and Timers
![[Pasted image 20231225224040.png]]
![[Pasted image 20231225224102.png]]
![[Pasted image 20231225224259.png]]
![[Pasted image 20231225224336.png]]
![[Pasted image 20231225224437.png]]

![[Pasted image 20231225224534.png]]

![[Pasted image 20231225224641.png]]
![[Pasted image 20231225224703.png]]
![[Pasted image 20231225224716.png]]
![[Pasted image 20231225224724.png]]

##### Best practices
![[Pasted image 20231225225802.png]]
![[Pasted image 20231225225814.png]]
![[Pasted image 20231225225825.png]]
![[Pasted image 20231225225833.png]]
![[Pasted image 20231225225856.png]]
![[Pasted image 20231225225911.png]]

![[Pasted image 20231225225935.png]]
![[Pasted image 20231225225948.png]]
![[Pasted image 20231225225956.png]]
![[Pasted image 20231225230011.png]]
![[Pasted image 20231225230022.png]]
![[Pasted image 20231225230033.png]]

##### Dataflow SQL & DataFrames
![[Pasted image 20231226145713.png]]
![[Pasted image 20231226150005.png]]
![[Pasted image 20231226150017.png]]
![[Pasted image 20231226150131.png]]
![[Pasted image 20231226150241.png]]
![[Pasted image 20231226150309.png]]
![[Pasted image 20231226150352.png]]
![[Pasted image 20231226150423.png]]
![[Pasted image 20231226150435.png]]
![[Pasted image 20231226150510.png]]
![[Pasted image 20231226150745.png]]
![[Pasted image 20231226150754.png]]
![[Pasted image 20231226150807.png]]
![[Pasted image 20231226150820.png]]
![[Pasted image 20231226150900.png]]
![[Pasted image 20231226150912.png]]
![[Pasted image 20231226150920.png]]
![[Pasted image 20231226150930.png]]
![[Pasted image 20231226150936.png]]
![[Pasted image 20231226151055.png]]
![[Pasted image 20231226151111.png]]
![[Pasted image 20231226151150.png]]
![[Pasted image 20231226151156.png]]
![[Pasted image 20231226151242.png]]
![[Pasted image 20231226151319.png]]
![[Pasted image 20231226151346.png]]
![[Pasted image 20231226151434.png]]

##### Beam notebooks
![[Pasted image 20231226152435.png]]
![[Pasted image 20231226152531.png]]
![[Pasted image 20231226152539.png]]
![[Pasted image 20231226152547.png]]
![[Pasted image 20231226152555.png]]
![[Pasted image 20231226152603.png]]
![[Pasted image 20231226152610.png]]
![[Pasted image 20231226152623.png]]

##### Monitoring
![[Pasted image 20231226192440.png]]
![[Pasted image 20231226192509.png]]
![[Pasted image 20231226192722.png]]
![[Pasted image 20231226192732.png]]
![[Pasted image 20231226192739.png]]
![[Pasted image 20231226192752.png]]
![[Pasted image 20231226192800.png]]![[Pasted image 20231226192812.png]]
![[Pasted image 20231226192818.png]]
![[Pasted image 20231226192837.png]]
![[Pasted image 20231226192904.png]]
![[Pasted image 20231226192925.png]]
![[Pasted image 20231226192934.png]]
![[Pasted image 20231226192950.png]]
##### Logging and Error Reporting
![[Pasted image 20231226212106.png]]
![[Pasted image 20231226212132.png]]
