# Write Skew


- Type of [[database]] [[race condition]]
- Occurs when two transactions read the same data, make disjoint updates based on what they read, but when combined these updates violate some invariant
	- Write skew involves transactions making conflicting writes based on what they read
	- Write skew can be prevented by taking write locks on the data each transaction read
- Grab the locks of all the relevant rows
- Another variation is phantom writes:
	-  Occurs when a transaction re-executes a query and gets different results because another transaction has added or removed rows that match the query's conditions
	- Phantom writes/reads involve rows appearing/disappearing between reads in the same transaction
	- Phantom writes often require more sophisticated solutions like predicate locks or index-range locks
---
Links :: [[Computer Science]] [[System Design]]
Reference :: https://www.youtube.com/watch?v=eym48yrObhY&list=PLjTveVh7FakLdTmm42TMxbN8PvVn5g4KJ&index=10&ab_channel=Jordanhasnolife
Type :: #atom
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-10-24 14:41
