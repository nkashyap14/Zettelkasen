- Also referred to as a shard, or a vnode
- In effect each partition is a small [[Database]] of its own
- Within each partition can keep keys in sorted order to make range scans easy
	- Also allows for treating the key as a concatenated index in order to fetch several related records in one query
---
Links :: [[Computer Science]] [[System Design]] [[Partitioning]]
Reference :: [[Designing Data Intensive Applications]]
Type :: #atom
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-05-31 15:02
