# Atomicity

- Concept in computer science to refer to something that can't be broken down into smaller parts or is atomic
- Ie one thread executes an atomic operation meaning no other thread can see the half-finished result of the operation
- In context of [[ACID]] atomicity describes what happens if a client wants to make several writes but a fault occurs after some of the writes have been processed
	- if writes are an atomic [[transaction]] than the transaction is aborted and the database must discard and undo any writes it has processed so far as part of that transaction
- Can be implemented using a log for crash recovery 
- Some databases offer complex atomic operations such as an increment operation which can remove the need for a [[read-modify-write cycle]] or a [[compare-and-set operation]]
	- allows us to prevent lost updates when multiple clients try to write to the same object [[Concurrency|concurrently]]

---
Links :: [[Computer Science]]
Reference ::
Type :: #atom
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-06-22 13:08
