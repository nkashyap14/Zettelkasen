# Read Committed Isolation

- A type of [[Database]] [[Isolation (ACID)]] that deals with [[dirty reads]] and [[Dirty Writes]]
	- When a thread reads uncommitted data that might be rolled back (dirty reads)
- This doesn't deal with [[read skew]]'s however. Those are considered acceptable under this
	- When a thread reads committed data but at different points in time creating an inconsistent view

---
Links :: [[Computer Science]]
Reference :: https://www.youtube.com/watch?v=oS60pr8H1e0&list=PLjTveVh7FakLdTmm42TMxbN8PvVn5g4KJ&index=8&ab_channel=Jordanhasnolife
Type :: #atom
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-10-24 13:12
