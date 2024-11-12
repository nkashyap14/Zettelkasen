# Dirty Writes

- When uncommitted writes are being overwritten by another writer [[thread]] which is due to a [[race condition]] on a [[Database]]
- This leads to an inconsistent state. Which breaks the [[ACID]] property guaranteed by databases
- One way to fix it is via Row Level [[locks]]
	- Grab the rows in same order

---
Links :: [[Computer Science]] [[System Design]]
Reference :: https://www.youtube.com/watch?v=oS60pr8H1e0&list=PLjTveVh7FakLdTmm42TMxbN8PvVn5g4KJ&index=8&ab_channel=Jordanhasnolife
Type :: #atom
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-10-24 13:04
