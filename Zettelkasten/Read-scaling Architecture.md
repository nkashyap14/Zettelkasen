
- [[Single-Leader|Leader Based Replication]] is utilized
	- Requires all writes to go to a single node but reads can go to any replica
- Great for workloads where there are only a small percentage of writes but read heavy
- Create many followers and distribute read requests across followers
- Removes load from the leader
- Can increase capacity/[[Scalability]] by adding more followers
- Only works realistically with [[Asynchronous replication]] as with syncrhonous replication a single node failure could reduce the system's [[Availability]]
- Issues:
	- Reading from asynchronous followers may lead to outdated/[[inconsistent]] data
		- Same query on leader and follower at the same time may get different results
		- Inconsistency is a termporary state
		- [[Eventual Consistency]]
---
Links :: [[Computer Science]] [[System Design]] [[Replication]] [[Single-Leader]]
Reference :: [[Designing Data Intensive Applications]]
Type :: #atom
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-05-31 15:11
