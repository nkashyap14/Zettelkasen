# Explicit Locking

- Another solution for lost update problem
	- Application explicitly locks objects that are going to be updated
	- Then perform [[read-modify-write cycle]] and any other transactions [[Concurrency|concurrently]] trying to read the same object are forced to wait
- Need to carefully think about application logic however as if you forget to add a necessary lock can lead to a [[race condition]]
---
Links :: [[Computer Science]] [[System Design]] [[lost update problem]]
Reference ::
Type :: #atom
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-07-04 09:09
