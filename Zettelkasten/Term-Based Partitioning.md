- Constructs a global index that covers data in all partitions
- Cant store that index on one node as then it becomes a [[Bottleneck]]
- You pick a term to partition on
	- ie color of car
	- color:red
		- partition 0 would take colors starting with letters a - r
		- partition 1 would take colors starting s to z
- The term we're looking for determines the partition
	- in the above case color:red would be the term we're looking from
- Can partition by index of term itself or the hash of the term
	- Partitioning by term is useful for range scans while the hash gives you a more even distribution of the load
- Advantage over [[Document Based Partitioning]] is that it can make reads more efficient rather than doing scatter / gather over all partiitons, client only needs to make a request to the specific partition
- In practice updates to the [[global index]] are generally [[asynchronous]]
---
Links :: [[Computer Science]] [[Partitioning Schemes]] [[Partitions]] [[System Design]] [[Secondary Index]]
Reference ::
Type :: #atom
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-06-14 12:45
