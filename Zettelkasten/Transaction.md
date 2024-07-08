# Transaction

# Transaction

## Summary

- Usually understood as a mechanism for grouping multiple operations on multiple objects into one unit of execution 
- Refers to a group of reads and writes that form a logical unit
- Access pattern became known as [[OLTP|online transaction processing]]
- Meant as a [[Fault Tolerance|fault tolerance mechanism]]
- All reads and writes are executed as one transaction
	- Either it succeeds/commits
	- Or it fails/aborts/rollsback
		- Point is to enable safe retries
	- Not all storage systems follow this roll back model
		- Datastores with [[Leaderless]] replication work on a best effort basis
			- Ie the datastore will do as much as it can and if it runs into an error won't undo anything
- Used to simplify programming model for applications accessing a database
- Safety guarantee's of transactions are best described by the [[ACID]] model
- Usually best understood as a mechanism for grouping multiple operations on multiple objects into one unit of execution

## Subtopics

- [[Single Object Transaction]]
- [[Multi Object Transaction]]
- [[Handling Errors for Transactions]]
- [[Weak Isolation Levels]]
- [[Write-Write Conflicts]]
## Details

## Conclusion


Type :: #topic
Links :: [[Computer Science]] [[Designing Data Intensive Applications]]
Creator ::
Date ::  2024-06-20 11:37