# Synchronous Replication

- Leader waits until follower has confirmed that it receives the write before reporting success to the user and making the write visible to other clients
- Advantage is that the follower is guaranteed to have an up-to-date copy of the data that is [[consistent]] with the leader
- Disadvantage is if follower doesn't respond, the write can't be processed and the leader must block all writes and wait for the replica to be online
	- Makes it impractical for all followers to be synchronous as any one node could cause the whole system to grind to a faull
	- In practice synchronous replication usually means one of the follolwers is synchronous and the rest asynchronous 
		- called [[semi-synchronous]]

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
