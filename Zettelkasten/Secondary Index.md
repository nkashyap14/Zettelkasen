# Secondary Index

- Do not map neatly to partitions
	- [[Partition Approaches for Secondary Index]]
- Bread and butter of relational databases + also common in [[Document Database]]
- In relational databases can create multiple secondary indexes on the same table
- Are crucial for performing joins efficiently
- Keys are not unique
- Both [[B-Tree]] and [[log-structured index]]s can be used as secondary indexes
- Key in a secondary index can be mapped to 2 things
	- The actual value: Row/Document/vertex in question
	- A reference to the row stored elsewhere
		- Usually place where row/document/vertex is stored is called a [[heap file]]
		- Stores data in no particular order
		- Common approach as it prevents duplication of data when multiple secondary indexes are at play
		- Efficient when updating value wihtout changing the key as record can be overwritten in place if not larger
			- If larger then it needs to be moved to a new location in the heap where there is enough space
				- then all indexes need to be updated to point at the new heap location or a forwarding pointer is left at the old heap loocation
		- Some situations the extra hop from the index to the heap file is too much of a penalty for reads so it can be desirable to store the indexed row directly within an index
			- Called [[Clustered Index]]
---
Links :: [[Computer Science]] [[Database]] [[relational database]]
Reference :: [[Designing Data Intensive Applications]]
Type :: #atom
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-04-21 12:46
