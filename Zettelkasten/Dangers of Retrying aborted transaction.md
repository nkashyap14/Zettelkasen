# Dangers of Retrying aborted transaction

- If transaction succeeded but network failed then retrying may duplicate the data so we may need an application level deduplication mechanism
- If the error is due to [[overload]] then retrying makes the problem worse
	- add a retry limit
	- use [[exponential backoff]]
- Transient errors are worth trying
	- [[deadlock]]
	- [[Isolation (ACID)|isolation violation]]
	- Network interruptions
	- [[failover]]
- Retrying a permanent error like a constraint violation is pointless
---
Links :: [[Computer Science]] [[System Design]] [[Transaction]]
Reference :: [[Designing Data Intensive Applications]]
Type :: #atom
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-07-01 20:35
