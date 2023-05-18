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


