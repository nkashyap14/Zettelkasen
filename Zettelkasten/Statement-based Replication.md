# Statement-based Replication

- [[Single-Leader|Leader]] logs every write request that it executes and sends that statement log to its folloewers
- For a [[relational database]] every insert, update, or delete statement is forwarded to followers and each follower parses and executes that [[SQL]] statement as if it had received it as a client
- Ways this can break:
	- Statement calls a non-deterministic function like NOW() to get current date or time or RAND()
	- Statements use an auto-incrementing column or they depend on existing data in the database that must be executed in exactly the same order on each replica
	- Statements that have side effects that may result in diffeerent side effects occurring on each replica
---
Links :: [[Computer Science]] [[Implementation of Replication Logs]] [[Replication]] [[System Design]]
Reference :: [[Designing Data Intensive Applications]]
Type :: #atom
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-05-31 15:29
