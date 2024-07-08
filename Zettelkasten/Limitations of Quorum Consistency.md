- w + r > n means every read returns the most recent value written for a key because there is at least one node that overlaps with the latest value\
- w + r <= n leads to more likelihood on reading stale values but allows for lower [[latency]] and higher [[availability]]
	- Database only becomes unavailable for reading or writing when reachable replicas fall below r or w
- Edge cases where stale values are returned for r + w > n
	- [[Sloppy quorum]]
		- w writes might end up on different nodes than r reads so no guaranteed overlap
	- Two concurrent writes means not clear which is first. safe solution is merge concurrent writes and pick winnerr
		- [[Detecting Concurrent Writes]]
	- Write happens concurrently with read
		- write may only be reflected on some of the replicas
---
Links :: [[Computer Science]] [[Leaderless]] [[Replication Algorithm's]] [[System Design]]
Reference :: [[Designing Data Intensive Applications]]
Type :: #atom
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-05-31 15:08