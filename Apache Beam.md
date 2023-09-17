![[Pasted image 20230307114910.png]]

Unified - same code for batch and streaming data
Portable - can work on multiple execution envs
Extensible - you can write extensions and connectors
Pipepline templates available
SDK
Model representation

##### Batch+strEAM
![[Pasted image 20230518121555.png]]
- Pipeline identifies data to be transformed
- PCollections are immutable collections of data processed by PTransforms
- Pipeline runners - container hosts, ie. [[Kubernetes]] - can be run on a local computer, VM, Cloud
- DF pipeline == directed graph of steps

![[Pasted image 20230518122215.png]]
[[Serialization]]
