# Dirty Reads

- When a [[Thread]] goes ahead and reads an uncommitted write in a [[Database]] 
- When a transaction reads data that has been written by another [[Concurrency|concurrent]] transaction that hasn't committed yet
	- If the other transaction rolls back the read data becomes invalid
- Fixes:
	- Store the old value on disk until the write is committed
		- Incurs some storage overhead however speeds up the db by nature of not having to resort to a lock
	- Row level locks
		- Avoid because locking is slow and this would bottleneck the db. Reads are much faster than writes so one slow write could bottleneck a bunch of reads

---
Links :: [[Computer Science]] [[System Design]]
Reference :: https://www.youtube.com/watch?v=oS60pr8H1e0&list=PLjTveVh7FakLdTmm42TMxbN8PvVn5g4KJ&index=8&ab_channel=Jordanhasnolife
Type :: #atom
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-10-24 13:07
