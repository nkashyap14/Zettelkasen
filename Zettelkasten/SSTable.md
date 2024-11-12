# SSTable

- Log structured storage segments being a sequence of key value pairs similar to [[Hash Index]]
- Difference is sequence of key-value pairs is now sorted by key
- Also required that each key only appears once within each merged segment file
- Advantages over log segments with hash indexes:
	- Merging segments is simple and efficient. Use merge sort algorithm
	- No longer need to keep an index of all keys in memory as keys are sorted
- To maintain a sorted structure in memory uses well known [[binary tree|tree]] data structures like [[Red-Black Tree]] or [[AVL Tree]]
	- In memory tree is sometimes called a mem table
	- When memtable gets bigger than some threshold it gets written to the disk as a SSTable file
- When serving readrequests check the current memtable, if not in there then check older segment, older segment and so on
	- To optimize the cases when you are looking up keys that are not in the db which can be slow you can maintain additional [[Bloom Filters]]
- If database crashes most recent writes crash
	- So to solve this keep an [[append only log]]
- Since data is in sorted order can efficiently perform range queries
- Disk writes are sequential so the tree supports high write throughput
---
Links :: [[Computer Science]] 
Reference :: [[Designing Data Intensive Applications]]
Type :: #atom
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-04-21 12:55
