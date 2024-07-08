# Hash Index

- Keep an in-memory [[hashmap]] where every key is mapped to a byte offset in the data file (location where the value can be found)
- When appending new key value pair to the file also update the hash map to reflect offset of data you just wrote
- Suited for situations where the value of each key is updated frequently
	- A lot of writes per key 
- Typically need to maintain the hash map in memory as a hash map on disk is difficult to make perform well as it requires a lot of random access I/O
---
Links :: [[Computer Science]] [[Data Formats]] 
Reference :: [[Designing Data Intensive Applications]]
Type :: #atom
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-04-21 12:48
