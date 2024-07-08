# dirty write

- Two [[transaction|transactions]] try to write to the same object in a database, typically later write should overwrite earlier write. In dirty write scenario if the earlier write is part of an uncommitted transaction than the later write might overwrite an uncommitted value
- By preventing this we avoid some kind of concurrency problems
---
Links :: [[Computer Science]] [[System Design]] [[Database]]
Reference :: [[Designing Data Intensive Applications]]
Type :: #atom
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-07-01 20:42
