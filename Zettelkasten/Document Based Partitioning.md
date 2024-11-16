# Document Based Partitioning

- Each document has an ID
- Partition by document ID
	- ie 0-499 in Partition 1, etc
	- Ranged based partitioning initial scheme
- Each partition then maintains its own secondary index which covers only the documents in that partition
	- Also known as a local index
- Issue is no reason why all records with specific x or y (like if you have a secondary index for color and you want all cars of color red) will map to the same partition. Can result in us having to send queries to all the partitions in order to gather results
	- Called scatter/gather
	- Can make read queries on document based secondary indexes expensive
	- DB Vendors recommend that you structure your partitioning scheme so that secondary index queries can be served from a single partition
- Advantage over [[Term-Based Partitioning]] is that the global index makes the writes slower and more complicated because a write to a single document may now affect multiple partitions of the index
	- every term might be on a different partition aka different node
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
