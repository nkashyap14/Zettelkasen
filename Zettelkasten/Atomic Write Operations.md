# Atomic Write Operations

- Many [[Database|databases]] provide atomic update operations which avoid implementing a [[read-modify-write cycle]] in application code
	- Usually the best solution
- [[Document Database|Document Databases]] like [[Mongodb]] provide atomic operations for making local modifications to a part of a [[JSON]] document
	- [[Redis]] offers [[Atomicity|atomic]] operations for modifying data structures like priority queues
- Usually implemented by taking an [[lock|exclusive lock]] on the object when it is read so that no other transaction can read it until the update has been applied.
	- [[cursor stability]]
	- Another option is to force all atomic operations to be executed on a single thread
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
