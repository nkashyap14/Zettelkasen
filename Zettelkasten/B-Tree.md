# B-Tree

- Most widely used indexing structure. Standard index implementation in almost all [[relational database]]
- Keep key value pairs sorted by key for efficient key value lookups and range queries
- Log structured indexes break databases into variable-sizee segments
- B-tree's break the database into fixed-size blocks or pages (traditionally 4 kb in size) and read or write one page at a time
- Each page can be identified using an address or location
	- Allows one page to refer to another but points to disk instead of memory
- If you want to update the value of an existing key you search for the leaf page containing that key and change the value in that page and write the page back to disk
	- any references to the page remain valid 
- A leaf page is a page containing individual keys which contains either the value for each key inline or contains references to the pages where each value can be found
- Leaf pages get split when they can't accommodate the range of keys when adding. However this is not an atomic operation because if db crashes after only writing some of the apges that results in a corrupted index
- To make the database resilient to crashes B-Tree implementations introduce a [[write-ahead log]] which is an append only file to which every modification must be written before applying to the pages of the tree itself
	- Used to restore the b-tree back to a consistent place
	- Means that every b-tree index must write every piece of data twice
---
Links :: [[Computer Science]] [[Index]]
Reference :: [[Designing Data Intensive Applications]]
Type :: #atom
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-04-21 13:10
