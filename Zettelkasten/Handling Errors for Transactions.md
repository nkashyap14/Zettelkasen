# Handling Errors for Transactions

## Summary

- Key feature of trasnaction is that it can be aborted and retried
	- if [[ACID]] is in danger of being violated easier to abandon transaction than let it continue
- Not the same in [[leaderless|leaderless replication models]]
	- they work on a best effort basis
		- database does as much as it can and if it runs into an error won't undo something
		- app job to recover from errors
## Subtopics

- [[Dangers of Retrying aborted transaction]]

## Details

## Conclusion


Type :: #topic
Links :: [[Computer Science]] [[System Design]]
Creator :: [[Designing Data Intensive Applications]]
Date ::  2024-07-01 20:33