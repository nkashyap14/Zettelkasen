# Read Committed

- Most basic level of transaction isolation
- 2 Guarantees
	- When reading from the data you will only see data that has been committed
		- no [[dirty read|dirty reads]]
	- When writing to the database you will only overwrite data that has been committed
		- no [[dirty write|dirty writes]]
- Does not prevent [[race condition]] between two counter increments
- Very popular isolation level
	- Default setting in Oracle11g, PostgreSQL, SQL Server 2012 + MemSQL
- [[Read Committed Concurrency Bugs]]
---
Links :: [[Computer Science]] [[System Design]] [[Weak Isolation Levels]] [[Isolation (ACID)]]
Reference :: [[Designing Data Intensive Applications]]
Type :: #atom
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-07-01 20:40
