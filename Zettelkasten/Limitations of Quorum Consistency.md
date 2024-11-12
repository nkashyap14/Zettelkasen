- w + r > n means every read returns the most recent value written for a key because there is at least one node that overlaps with the latest value
- w + r <= n leads to more likelihood on reading stale values but allows for lower [[latency]] and higher [[availability]]
	- Database only becomes unavailable for reading or writing when reachable replicas fall below r or w
- Edge cases where stale values are returned for r + w > n
	- [[Sloppy quorum]]
		- w writes might end up on different nodes than r reads so no guaranteed overlap
	- Two concurrent writes means not clear which is first. safe solution is merge concurrent writes and pick winner
		- [[Detecting Concurrent Writes]]
	- Write happens concurrently with read
		- write may only be reflected on some of the replicas
		- Undetermined whether the read returns the old or the new value
	- Write succeeded on some replicas but failed on others and succeeded on overall less than w replicas
		- not rolled  back on the replicas where it succeeded
		- subsequent reads may or may not return the value from that write
	- Node carrying a new value fails and its data is restored from a replica carrying an old value
		- number of replicas storing new value may fall below w
- Due to these edge cases [[Leaderless]] replication style db's like [[Dynamodb]] are generally optimized for application use cases that can tolerate [[Eventual Consistency]]
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