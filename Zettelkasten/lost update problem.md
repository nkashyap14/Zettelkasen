# lost update problem

- Occurs if an application reads value from the database, modifies it, and then writes back the modified value
	- [[read-modify-write cycle]]
- If two transactions do this [[Concurrency|concurrently]] than one of the modifications can be lost because the second write does not include the first modification
	- later write clobbers the earlier write
- Common pattern
	- [[Incrementing a counter]]
	- [[Updating an account balance]]
	- Local change to complex value
		- Adding element to a list within a json doc
	- Two users editing a wiki pagea t the same time

---
Links :: [[Computer Science]] [[Database]] [[System Design]] [[Distributed System]]
Reference :: [[Designing Data Intensive Applications]]
Type :: #atom
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-07-04 09:07
