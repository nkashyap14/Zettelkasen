# Automatic Failover

- First determine that the leader has failed
	- no fool proof way
	- [[heartbeat protocol]]
- Choose a new leader
	- Election process where replicas choose new leader
	- Or a [[controller node]] can appoint new leader
		- controller node being elected previusly
	- Best candidate for new leader is replica with most up to date changes
- Reconfigure system to use new leader
	- make old leader a follower as well that recognizes new leader

---
Links :: [[Computer Science]] [[Horizontal Scaling]] [[Single-Leader]] [[Multi-Leader]]
Reference :: [[Designing Data Intensive Applications]]
Type :: #atom
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-05-31 15:20
