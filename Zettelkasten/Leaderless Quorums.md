- N replicas
- w nodes must confirm a write for it to be successful
- r nodes must be queried for each read
$$
w + r > n = Live Data
$$
- Allows system to tolerate unavailable nodes as follows:
	- w < n = can still process writes if a node is unavailable
	- r < n = can still process writes if a node is unavailable
	- n = 3, w = 2, r = 2 = 1 unavilable node
	- n = 5, w = 3, r = 3 means 2 unavailable nodes tolerable
- Normally n replicas are sent reads + writes in parallel
	- R + W just determine how many we wait for
- Means one of the r nodes we're reading from must be up to date 
- r/w can be though of as the minimum number of votes required for a read or write to be valid
- Common choice:
	- make n odd
		- 3 or 5
	- set w = r  (n + 1) /2 
		- rounded up
- Workload with few writes and many reads
	- Set w = n
	- r = 1
	- Means quick reads
	- however even one failed node causes all writes to fail
- [[Limitations of Quorum Consistency]]
- Basically we can think of r + w as tuning parameters that allow us to adjust the probability of stale values being read however they are not absolute guarantees
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