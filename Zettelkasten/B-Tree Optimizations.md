# B-Tree Optimizations

- Instead of overwriting pages and maintaining a [[write-ahead log]] you can use a [[copy-on-write]] scheme.
	- Modified page is written to a different location and a new version of parent pages is created pointing at the new location
	- Useful for concurrency control
- Save space in pages by not storing the entire key but abbreviating it
	- Pages on interior keys only need to provide enough information to act as boundaries between key ranges
	- Pack more keys into a page and allow the tree to have a higher branching factor and lower levels due tot hat
- Pages can be positioned anywhere on disk. Query needs to scan over a large part of the key range in sorted order can be inefficient because a disk seek may be required all over for every page read
	- Implementations therefore try to lay out the tree so that leaf pages appear in sequential order on the disk
	- It is easier for [[SSTable]] to keep sequential keys nearby on disk as they rewrite large segments of storage during merging
	- Becomes harder as tree grows larger
- Add additional pointers to the tree ie maybe leaf page has references to sibling pages which can allow for scanning keys in order without jumping to parent pages

---
Links :: [[Computer Science]]  [[System Design]] [[B-Tree]] [[Index]]
Reference ::
Type :: #atom
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-11-02 08:40
