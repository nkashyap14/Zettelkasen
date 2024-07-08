# Consistency (ACID)

- In the context of ACID consistency refers to an application specific notion of the database being in a good state 
- Idea is that there are certain statements about data, [[invariants]], that must always be true
- Depends on the application's idea of invariants, and it is the applications repsponsibility to define its transactions to preserve consistency
- Also can be understood as that after a successful write, update, or delete of a record any read request immediately receives the latest value of a record
	- more cap theorem related

---
Links :: [[Computer Science]] [[ACID]]
Reference ::
Type :: #atom
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-06-22 13:11
