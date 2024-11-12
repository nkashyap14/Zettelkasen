# In Memory Key Value Stores


- [[Memcached]] is one
	- Used as a caching use only where its acceptable for data to be lost if a machine is restarted
	- There are versions that aim for [[Durability]] which can be achieved with special hardware or techniques
		- Battery Powered RAM
		- Writing a log of changes to disk
		- Periodic snapshots to disk
		- Replicating in memory state to other machines
- [[Redis]] is an in memory key value store that provides weak durability by writing to disk asynchronously
- Reads are served from memory which increases read [[Throughput]]
- [[RAM]] has become cheaper over time making it so that some smaller datasets are becoming feasible to keep in [[memory]] even perhaps distributed over a few servers 
---
Links :: [[Computer Science]] [[System Design]]
Reference :: [[Designing Data Intensive Applications]]
Type :: #atom
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-11-08 17:55
