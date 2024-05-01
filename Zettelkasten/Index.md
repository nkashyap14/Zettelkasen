# Index

- Type of [[Data Structures|data structure]] 
- General idea is keep some additional metadata on the side which can act as a signpost and help us locate data we want in a faster manner
- Additional structure that is derived from the primary data
- Additional structure is overhead especially on writes
	- For writes hard to beat performance of appending to a file. Any index slows down writes because the index must be updated every time a write occurs as well
- Well chosen indexes speed up read queries but every index slows down writes
- The key in an index is thing queries search for, value can be one of two things
	- Actual row
	- Or a reference to the row stored elsewhere
		- In this case place where rows are stored are known as a heap file
- Types of indexes:
	- [[Log Structured Indexes]]
		- [[Hash Index]]
		- [[SSTable|Sorted String Table]]
	- [[B-Tree]]
	- [[Secondary Index]]
	- [[Clustered Index]]
		- When the extra hop from the index to the heap file is too much a peformance penalty for reads so we store indexed row directly within an index
	- [[Multi-Column Index]]
		- Also referred to as a concatenated index
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
