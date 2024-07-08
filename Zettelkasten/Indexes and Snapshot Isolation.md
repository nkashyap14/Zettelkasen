# Indexes and Snapshot Isolation

- Essentially a snapshot isolation is a [[multiversion datatbase]]
- Results in changes on how [[index|indexes]] work
	- One option is to have index point to all versions of an object
		- Then index query needs to filter out non relevant object versions for each [[transaction]]
		- When [[garbage collector]] removes old object versions that aren't visible to any transaction then the corresponding index entries can be removed
---
Links :: [[Computer Science]] [[System Design]]
Reference :: [[Designing Data Intensive Applications]]
Type :: #atom
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-07-04 08:57
