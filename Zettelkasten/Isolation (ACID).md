# Isolation (ACID)

- Isolation in the context of [[ACID]] means that concurrently executing [[Transaction|transactions]] are isolated from each other and do not step on each other's toes
	- Result is same as if they had run [[serially]] even though in reality they may have run concurrently and executed on shared portions of data
- Can be implemented by using a lock on each object allowing only one thread to access an object at a time

---
Links :: [[Computer Science]] [[System Design]] [[ACID]]
Reference :: [[Designing Data Intensive Applications]]
Type :: #atom
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-06-22 13:14
