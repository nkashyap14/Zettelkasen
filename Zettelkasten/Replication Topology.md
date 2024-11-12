- Describes the communication paths along which writes are propagated from one node to another
- With more than one leader can lead to various topologies
- Most common is [[all-to-all]]
	- every leader sends its writes to all other leaders
	- More fault tolerant as it is densely connected
	- Issues:
		- some network links may be faster than others
			- some replication messages may overtake others
			- Can be alleviated via a technique called [[version vectors]]
- Other topologies are [[circular topology]]
	- all nodes receive writes from one node and forwards those writes to one node
- [[Star Topology]]
	- One root node forwards all writes to other nodes
- in circular and star topologies a write may need to pass through several nodes before it reaches all replicas
	- Nodes need to forward data changes
	- To prevent replication loops each node is given a unique id and in the replication log each write is tagged with identifiers of nodes it has passed through
	- node receives a data change tagged with its own id it ignores it
	- Issue with these topologies is that one node failure can interrupt the flow of replication messages
		- could be reconfigured but would need to be done manually
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