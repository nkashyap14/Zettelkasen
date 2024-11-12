# Storage Engine

## Summary

- Underlying software component that a [[Database]] uses to create, read, update, and delete ([[CRUD]]) data from a database
- Most databases have their own [[API]] that allows the user to interact with their underlying engine
## Subtopics

- Two main families of storage engines on [[OLTP]] side:
	- [[Log-Structured Storage Engine]]
		- Only permits appending to files and deleting obsolete files
	- [[Page-Oriented Storage Engine]]
		- Update in place school
		- Treats the disk as fixed size pages which can be overwritten
		- [[B-Tree]]
- Two broad categories:
	- Optimizied for [[OLTP]]
		- user facing so might see a huge volume of requests
		- applications usually only touch a small number of records in each query
		- Disk seek time is often the bottleneck here
	- Optimized for [[OLAP]]
		- Disk bandwidth is often the bottleneck here
		- Column oriented storage is a popular solution here
		- Handle a lower amount of queries but each query is usually demanding
## Details

## Conclusion


Type :: #topic
Links :: [[Computer Science]] [[Designing Data Intensive Applications]]
Creator ::
Date ::  2024-10-23 10:44