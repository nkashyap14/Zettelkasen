# ACID

- Stands for:
	- [[Atomicity]]
		- Something that can not be broken down into smaller parts
	- [[Consistency (ACID)]]
	- [[Isolation (ACID)]]
	- [[Durability (ACID)]]
- Coined in 1983 by Theo Harder and Andreas Reuter in an effort to establish precise terminology for fault-tolerance mechanisms in databases
- Just defines property, one databases implementation of ACID can be different from another
- There is ambiguity in the isolation term
- Systems that do not meet ACID are sometimes called [[BASE]]
	- Stands for Basically Available, Soft State, and Eventual Consistency
- Atomicity and Isolation describe what the database should do if a client makes several writes within the same transaction
	- Atomicity
		- If error occurs halfway through sequence transaction should be aborted
		- All or nothing guarantee
	- Isolation
		- Concurrently running transactions shouldn't interfere with each other 
		- Ie if one transaction makes several writes other transaction should either see none or all of those writes, never a subset
---
Links :: [[Computer Science]] [[System Design]] [[relational database]]
Reference :: [[Designing Data Intensive Applications]]
Type :: #atom
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-06-22 13:05
