![[Pasted image 20230329141352.png]]
- built-in support for Hadoop
- managed hardware and configuration
- simplified version management
- flexible job configuration

##### Running Hadoop on Dataproc
- DP can be used to migrate Spark jobs
![[Pasted image 20230329145325.png]]
- pre-configured optional components (to be declated when deploying DataProc)
- ![[Pasted image 20230329145634.png]]
- data should be sent to cluster buckets, tables or data warehouse
	- ![[Pasted image 20230329145751.png]]
- Dataproc steps
	  ![[Pasted image 20230329145905.png]]
	- Setup
	  ![[Pasted image 20230329145918.png]]
	- Configure
	  ![[Pasted image 20230329145959.png]]
	  - Optimize
	    ![[Pasted image 20230329150050.png]]
	-  Utilize
	  ![[Pasted image 20230329150115.png]]
	  - Monitor
	    ![[Pasted image 20230329150146.png]]
##### Optimizing DataProc
- you want to have cluster close to your data (region/zone)
- check of there are any rules applied to network, like small # of VPN gateways before reaching the cluster
- don't use DataProc for more than 10,000 files
- make sure the persistent disk won't limit throughput
- make sure you allocated enough VMs to the cluster

##### Optimizing DataProc Storage
![[Pasted image 20230408211231.png]]
- DataProc + CloudStorage reduces the disk requirement and save costs
![[Pasted image 20230408211650.png]]
![[Pasted image 20230408211837.png]]
- migrating from ling-live clusters to short-lived clusters built for specific jobs (ephemeral model)
- cluster scheduled deletion - set a timer after an idle cluster is deleted
![[Pasted image 20230408212056.png]]
![[Pasted image 20230408212144.png]]

##### Optimizing Dataproc Templates and Autoscaling
![[Pasted image 20230408212253.png]]
- The workflow template becomes active when it is in stanciated into the DAG. 
- The template can be submitted multiple times with different parameter values.
![[Pasted image 20230408212509.png]]
![[Pasted image 20230408212632.png]]

##### Optimizing Dataproc Monitoring
- available in logging
- create labels to find logs
![[Pasted image 20230408212857.png]]