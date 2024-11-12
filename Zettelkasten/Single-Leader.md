# Single-Leader

- Also referred to as leader-based replication
- Also called [[active/passive]]
- Also called [[master-slave]] replication
- One of the replicas is designated as leader/master/primary
	- Writes sent to leader which writes new data to its local storage
- Other replicas are known as followers/read replicas/slaves/hot standbys
	- When leader writes new data it also sends data change to followers as part of a [[replication log]] or [[change stream]]
- Clients can query either the leader or follower
	- writes only to leader
- Common feature of replication built into many relational db's like [[PostgreSQL]], [[MySQL]] and more
- Also used in some [[nonrelational databases]] like [[Mongodb]]
- Also used in some [[Message Broker]]s like [[Kafka]]
- Good for workloads that consist of mostly reads and only a small percentage of writes
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
