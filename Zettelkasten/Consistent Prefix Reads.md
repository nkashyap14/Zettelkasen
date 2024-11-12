# Consistent Prefix Reads

##### Definition:

- A type of [[Consistency]] guarantee that says that if a sequence of writes happen in a certain order than anyone reading those writes will see them in the same order
- A problem in [[Partitioning|partitioned databases]]
	- different partitions operate independently so there is no global ordering of writes
	- user may see parts of the database in an older state and some in a newer state
	- one solution is to make sure that causally related writes are written to the same partition
		- Requires some sort of distributed transaction with a guarantee like [[Snapshot Isolation]]


Type :: #topic
Links :: [[Computer Science]]
Book :: [[Designing Data Intensive Applications]]
Date ::  2024-11-11 14:33