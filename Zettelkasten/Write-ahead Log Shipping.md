- Log is an append-only sequence of bytes containing all writes to the database
- Use the exact same log to build a replica on another node 
- Leader writes the log to disk + sends it across [[network]] to its followers
- When the follower processes the log it builds a copy of the exact same structures as found on the leader 
- Disadvantage:
	- Describes data on a very low level aka what bytes changed in which disk block
	- Replication gets coupled to the storage engine so we can't change storage format from one version to another 
---
Links :: [[Computer Science]] [[Implementation of Replication Logs]] [[Replication]] [[System Design]]
Reference :: [[Designing Data Intensive Applications]]
Type :: #atom
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-05-31 15:29
