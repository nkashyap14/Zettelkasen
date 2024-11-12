# Comparing B-Tree and SSTables

- SSTables Can sustain a much higher throughput of random writes compared to B-Tree's because they turn random writes into sequential writes on the underlying device
	- Better for applications with higher write throughput
	- General rule SSTables/LSM-Trees faster for writes while B-Trees are thought to be faster for reads
- Downside of SSTables and log-structured storage is that log compaction can interfere with the performance of ongoing reads and writes
	- B-Trees can be more predictable
- Advantage of B-Tree is that each key exists in only one place in the [[index]]
	- Log structured engine might have multiple copies of the same key in different segments
	- B-Tree is better for databases that want to offer strong transactional semantics
		- Many relational databases have transaction isolation implemented using locks on ranges of keys and B-Tree's can have the locks directly attached to the keys

---
Links :: [[Computer Science]] [[B-Tree]] [[SSTable]]
Reference ::
Type :: #atom
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-11-02 08:45
