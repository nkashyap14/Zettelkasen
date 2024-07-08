# rebalancing

- Process of moving data between nodes in a cluster
- Needs to meet minimum requirements regardless of [[Partitioning Schemes|Partitioning Scheme]] used
	- Load (Data storage + Read and Write requests) should be shared fairly between the nodes in a cluster
	- DB should continue accepting reads and writes while the rebalancing is happening
	- Don't move more data than necessary as otherwise it can overload the [[network]]

---
Links :: [[Computer Science]] [[System Design]] [[Horizontal Scaling]] [[Rebalancing Partitions]]
Reference :: [[Designing Data Intensive Applications]]
Type :: #atom
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-06-17 09:21
