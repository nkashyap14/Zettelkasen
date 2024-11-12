# Replication

- Keep a copy of the same data on several different nodes potentially in different locations
- Reasons for utilizing replication
	- [[Scalability]]
	- [[Latency]] reduction
	- [[Availability]]
- Provides [[redundancy]]
	- Multiple failovers
	-  If nodes become unavailable data can be served from remaining nodes
- Can also help improve performance
- Every write to a database needs to be processed by every replica in order to keep them in sync
- [[Reasons to Replicate Data]]
- [[Replication Difficulties]]
- [[Setting up new followers (Replication)]]
- [[Handling Node Outages (Replication)]]
- [[Implementation of Replication Logs]]
- [[Replication Algorithm's]]
- [[Asynchronous replication]]
- [[Synchronous Replication]]
- [[Failed replica handling]]
- [[Replication Lag]]
- [[Read-scaling Architecture]]
- [[Detecting Concurrent Writes]]
- One of the two common ways  that data is distributed across multiple nodes
	- Other is [[Partitioning]]
---
Links :: [[Computer Science]] [[System Design]] [[Data]] [[Database]]
Reference :: [[Designing Data Intensive Applications]]
Type :: #atom
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-05-31 15:02
