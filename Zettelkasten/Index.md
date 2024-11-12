# Index

- Type of [[Data Structures|data structure]] 
- General idea is keep some additional metadata on the side which can act as a signpost and help us locate data we want in a faster manner
- Additional structure that is derived from the primary data
- Additional structure is overhead especially on writes
	- For writes hard to beat performance of appending to a file. Any index slows down writes because the index must be updated every time a write occurs as well
- Well chosen indexes speed up read queries but every index slows down writes
	- Tree indexes tend to take looks up from a linear time scan to a log(n) scan which is huge when dealing with n's that get extremely large
- The key in an index is thing queries search for, value can be one of two things
	- Actual row
	- Or a reference to the row stored elsewhere
		- In this case place where rows are stored are known as a heap file
- Key-Value indexes are like a primary key in the relational model. A unique primary key gets mapped to one row, or one document in a document db, or one vertex in a graph db.
- 3 Main Key-Value Indexes to commit to memory:
	- SSTables + LSM Tree (In memory balanced binary tree implemented with red/black tree or avl tree)
		- Pro: Number of keys not limited by memory
		- Fast writes to memory compared to b-trees slow compared to hash index
		- Supports range queries but slow compared to b-trees as you need to check all SSTables
		- Negative : Extra cpu usage for compaction of sstables when merging sstable files together
	- Hash Index
		- Pro: O(1) reads and writes in memory
		- Negative: Keys need to fit in memory
		- Negative: No range queries
	- B-Tree
		- Pro: Fast range queries
		- Pro: Number of keys not limited by memory
		- Negative: Slow writes to b-tree on disk
- Types of indexes:
	- [[Log Structured Indexes]]
		- [[Hash Index]]
		- [[SSTable|Sorted String Table]]
	- [[B-Tree]]
	- [[Secondary Index]]
	- [[Clustered Index]]
		- When the extra hop from the index to the heap file is too much a peformance penalty for reads so we store indexed row directly within an index
		- In practice you are more likely to see indexing by addressing where the look up points to a location in heap memory where the row data is
		- Overhead requires duplication of row data
	- [[Multi-Column Index]]
		- Also referred to as a concatenated index or composite index
	- [[Fuzzy Index]]
		- For cases when you need to search for similar keys not just exact

---
Links :: [[Computer Science]] [[Database]] [[relational database]]
Reference :: [[Designing Data Intensive Applications]]
Type :: #atom
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-04-21 12:46
