# Weak Isolation Levels

- Concurrency bugs are hard to find so databases try to hide these issues by providing [[transaction isolation]]
	- means that its serializable isolation aka transactions have same effect as if they run serially one at a time
	- Comes with a performance cost and some databases don't want to pay the price
- Some databases offer weaker levels of isolation which protect against some concurrency issues but not all
- See:
	- [[Read Committed]]
---
Links :: [[Computer Science]] [[System Design]] [[race condition]]
Reference :: [[Designing Data Intensive Applications]]
Type :: #atom
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-07-01 20:37
