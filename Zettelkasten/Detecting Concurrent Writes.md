- Dynamo-style databases allow several clients to write concurrently to the same key meaning conflicts may arrise
- Events may arrive in different order at different nodes based on variable network delays and partial failures
- Need to have convergence towards the same state
- Options:
	- [[Last Write Wins]]
		- Each replica only stores most recent value
		- need unambigous way to determine which is the more recent write
		- Costs durability as even if there are several concurrent writes reported as successful only one survives and others are discarded
		- Treat databsaes with LWW if need for no losing data as keys being immutable once being placed
		- Achieves goal of eventual convergence but at the cost of durability
	- [[version vectors]]
		- Version number per replica as well as per key
		- each replica increments its verison number when processing a write
		- Keeps track of version number it has seen from other replicas
		- Can use that info to figure out which values to overwrite and which values to keep as sibling
			- generally if between two version vectors neither of the version vector is >= than the other where all indexes >= all indexes of other version vector than they are said to be [[Concurrency|concurrent]]
			- Version vectors are sent from the database replicas to clients when values are read and need to be sent back to the database when a value is subsequently written
				- Allows the distinguishing between overwrites and concurrent writes
		- From there we can store siblings on concurrent writes and than the applicatiaon can merge siblings
	- [[CDRT's]]
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
