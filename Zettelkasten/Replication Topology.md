- Describes the communication paths along which writes are propagated from one node to another
- With more than one leader can lead to various topologies
- Most common is [[all-to-all]]
	- every leader sends its writes to all other leaders
- Other topologies are [[circular topology]]
	- all nodes receive writes from one node and forwards those writes to one node
- [[Star Topology]]
	- One root node forwards all writes to other nodes
---
Links :: [[Computer Science]] [[Multi-Leader]] [[Replication Algorithm's]] [[Replication]] [[System Design]]
Reference :: [[Designing Data Intensive Applications]]
Type :: #atom
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-05-31 15:08