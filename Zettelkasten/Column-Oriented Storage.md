# Column-Oriented Storage

- In most [[OLTP]] databases storage is laid out in a row-oriented fashion where all the values from one row of a table are stored next to each other
	- [[Document Database]]'s store entire documents as one contiguous section of bytes
- In column oriented storage store all the values from each column together instead
	- allows for a query needing to only read and parse columns used in a query saving a lot of work
- [[Column Compression]]

---
Links :: [[Computer Science]] [[Data Models]]
Reference :: [[Designing Data Intensive Applications]]
Type :: #atom
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-04-27 13:13
