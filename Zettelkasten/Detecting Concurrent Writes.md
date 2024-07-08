- Dynamo-style databases allow several clients to write concurrently to the same key meaning conflicts may arrise
- Events may arrive in different order at different nodes based on variable network delays and partial failures
- Need to have convergence towards the same state
- Options:
	- [[Last Write Wins]]
		- Each replica only stores most recent value
		- need unambigous way to determine which is the more recent write
		- Costs durability as even if there are several concurrent writes reported as successful only one survives and others are discarded
		- Treat databsaes with LWW if need for no losing data as keys being immutable once being placed
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
