# Snapshot Isolation

## Summary

- Most common solution to [[Read Committed Concurrency Bugs]]
	- Aka [[read skew]] or [[non-repeatable read]]
- Idea is that each [[Transaction]] reads from a [[consistent snapshot]] of the database
	- All the data committed in a database at a particular point in time
- Even if data is changed by later transactions each transaction sees the old data from the time when the transaction started
- Useful for long-running, [[read-only queries]], like backups, and analytics
## Subtopics

- Popular feature supported by [[PostgreSQL]], [[MySQL]] with [[InnoDB storage engine]], [[Oracle]], [[SQL Server]]
- Implementations typically use [[write locks]] to prevent [[dirty write|dirty writes]]
	- Means transactions that make a write can block progress of another transaction that writes to the same object
- No locks for reads
- [[Visibility rules for observing a consistent snapshot]]
- [[Indexes and Snapshot Isolation]]

## Details

- Also referred to as Multiversion Concurrency Control
	- Also referred to as serializable in oracle
	- Called [[repeatable read]] in PostgreSQL and MySQL
- Readers never block writers and writers never block readers
	- Allows a database to handle long running read queries on a consistent snapshot while also processing writes normally
		- No lock contention between the two

## Conclusion


Type :: #topic
Links :: [[Computer Science]] [[Designing Data Intensive Applications]]
Creator ::
Date ::  2024-07-04 08:41