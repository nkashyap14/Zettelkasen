- Network interruption can cut a client off from large number of db nodes which are still alive.
	- So r or w reachable nodes do not remain
- Decision becomes should it be better to return errors for all requests or to accept writes anyways and write them to some nodes that are reachable
	- second part is known as a sloppy quorum
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