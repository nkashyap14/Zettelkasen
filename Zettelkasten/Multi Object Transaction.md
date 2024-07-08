# Multi Object Transaction

- A transaction in which we need to modify several objects (row, document, or records) in a database at once
	- Need [[Isolation (ACID)]] + [[Atomicity]]
- Require some way of determining which read and write operations belong to the same transaction
	- For [[relational database]]'s this is done based on the client's [[TCP]] connection to the database
		- Everything between a BEGIN TRANSACTION and a COMMIT is considered to be part of hte same transaction
	- For [[nonrelational databases]] they often don't have a way of grouping those operations together so without the transaction mechanics there are instances where commands may succeed for some keys and not others leaving the database in a partially updated state
#### Need for Multi Object Transactions
- Rows with foreign keys so if inserting several records that refer to each other the foreign keys have to be correct and up to date
- Databases with secondary indexes
	- From the transaction point of view the secondary indexes are different database objects
---
Links :: [[Computer Science]] [[System Design]] [[Transaction]]
Reference :: [[Designing Data Intensive Applications]]
Type :: #atom
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-06-23 07:31
