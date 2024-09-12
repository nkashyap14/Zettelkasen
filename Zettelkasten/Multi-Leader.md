- Allow more than one node to accept writes
- Replication still happens in the same way in that each node that processes a write must forward that data change to all other nodes
- Also called master-master replication or active/active
- Rarely makes sense in a single data center environment as benefits are outweighed by complexity
- Use cases:
	- Multiple data center operation
		- Put a leader in each data center
		- Within data center leader follower replication
		- Across data centers leader to leader replication of changes'
	- Clients with offline operation
		- ie calendar apps on phones where you need to be able to see meetings scheduled regardless of network connection
		- In this case each client has a local db that acts as a leader (accepts write requests) and there is asynchronous multi-leader replication process between replicas on the calendars on all devices
- Issue:
	- Write conflict of simultaneous editing
		- If you change the propagation of writes to be synchronous could alleviate write conflicts however it would reduce pro of having multiple write nodes
		- Best way to resolve is to prevent it from happening. Ensure all writes for a particular record go through the same leader
- [[Replication Topology]]
---
Links :: [[Computer Science]] [[Algorithm]] [[Replication Algorithm's]] [[Replication]] [[System Design]]
Reference :: [[Designing Data Intensive Applications]]
Type :: #atom
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-05-31 15:08