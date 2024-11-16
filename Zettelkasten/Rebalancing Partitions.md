# Rebalancing Partitions

## Summary

- Database requirements are constantly evolving:
	- Ie if query throughput increases leads to needing mroe [[Vertical scaling]] with additions of more CPU's
	- If dataset size increases need to add more disks and ram
	- A machine fails and other machines need to take over failed machine's responsibilities
		- [[Horizontal Scaling]]
- All of above can lead to needing [[rebalancing]]
## Subtopics

- [[Hash Mod N]]
	- Don't do it this way
	- Not good for [[Range Based Partitioning]]
	- If number of nodes change than most of the keys would need to be moved from one node to another
- Fixed partitioning:
	- Create a fixed number of partitions in the first place for the cluster
	- When a node is added than it just needs to steal a few partitions from every existing node until partitions are fairly distributed again
	- Number of partitions never changes
	- Nor does the key assignment to partition. Only partitions are moved between nodes
	- Number of partitions configured at the outset is the maximum number of nodes the cluster can have so need to choose a large number to accommodate for future growth
	- Works well with hash partitioning because the hash function ensures that keys are distributed across the whole range of possible hashes
	- Inconvenient for databases that use [[Range Based Partitioning]] as if boundaries are set wrong then all the data could end up on one partition
- [[Dynamic Partitioning]]
	- Good for [[Range Based Partitioning]]
- [[Consistent Hashing]]
## Details

## Conclusion


Type :: #topic
Links :: [[Computer Science]] [[System Design]] [[Partitioning]]
Creator ::
Date ::  2024-06-07 13:05