# Hash Mod N

- Hash(key) mod N to distribute over [[node|nodes]] in a [[network]] 
- Issue is if the number of nodes N changes than most of the keys end up needing to be moved from one node to another
- Can solve this by having a fixed number of partitions which are greater than there are nodes
	- Assign several partitions to each node
	- Now if a new node is added than the node can steal a few partitions from the each node until partitions are fairly distributed again
- [[Fixed Partition Databases]]
	- Style where databases start with a fixed number of partitions
	- Number of partitions configured at the outset is the maximum number of nodes you can have
	- [[Cassandra]]
		- is an example of a db in this style

---
Links :: [[Computer Science]] [[Partitioning Schemes]] [[hash functions]] [[Partitions]]
Reference ::
Type :: #atom
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-06-17 09:24
