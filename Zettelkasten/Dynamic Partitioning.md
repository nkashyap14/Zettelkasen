# Dynamic Partitioning

- [[Range Based Partitioning]] databases create partitions dynamically 
	- When a partition grows to exceed some sort of configured size then its split into two partitions so that half of the data ends up on each side of the split
	- Each partition gets assigned to one [[node]]
	- One half is transferred to another node to balance the load
- Advantage:
	- Number of partitions adapts to data volume
	- Empty database starts off with a single partition
		- While dataset remains small all writes are processed by one node while other nodes sit idle
- Can work with [[Hash Based Partitioning]] as well
---
Links :: [[Computer Science]] [[Partitioning Schemes]] [[System Design]]
Reference :: [[Designing Data Intensive Applications]]
Type :: #atom
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-06-17 09:33
