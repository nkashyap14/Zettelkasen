# Partitioning

- Used to improve a systems [[Scalability]]
- Main goal of partitioning is to spread the data load and the query load evenly across multiple machines allowing us to avoid hotspots 
	- If each node takes a fair share, 10 nodes, than ten nodes should be able to handle ten times as much data and ten times the read and write throughput of a single node
	- Leads to us needing to pick a [[Partitioning Schemes]] that is appropriate for our data and [[rebalancing]] the partitions as well from time to time as nodes are added or removed
- Small queries that operate on a single partition; each node can independently execute the queries for its own partition
	- allows query throughput to be scaled by adding more nodes 
- Large complex queries can potentially be parallelized across many nodes but this is difficult
- Splitting a big database into smaller subsets called partitions
- Allows different partitions to be assigned to different nodes
	- called [[sharding]]
- Designed so that each piece of data belongs to exactly one partition
- Designed to improve [[Scalability]]
- Great for [[Shared-Nothing Architecture]]
- Allows for the query load to be distributed across [[multiprocessing|many processors]]
- usually combined with [[Replication]] so that copies of partitions are stored on multiple nodes
	- used to improve [[Fault Tolerance]]
- Can have unfair or skewed partitioning
	- Example extreme case all the write loads end up on one partition
	- Ends up that n -1 nodes are idle and only 1 node services all writes
- [[Partitioning Schemes]]
- [[Partitioning and Secondary Indexes]]
- [[Rebalancing Partitions]]
- [[Vertical Partitioning]]
- [[Horizontal Partitioning]]
---
Links :: [[Computer Science]] [[System Design]] [[Partitions]]
Reference :: [[Designing Data Intensive Applications]]
Type :: #atom
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-05-31 15:02
