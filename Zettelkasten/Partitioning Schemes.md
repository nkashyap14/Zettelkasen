# Partitioning Schemes

## Summary

## Subtopics

- [[Range Based Partitioning]]
	- [[Partitions|Partition]] by ranges of keys
		- Issue is ranges may not be evenly distributed because underlying data is not evenly distributed
		- Bad performance for range queries that use the partitioning keys when the queried range is big and resides on multiple nodes
	- Certain access patterns can lead to [[hotspots]]
- [[Hash Based Partitioning]]
	- Many [[distributed data stores]] use [[hash functions]] to determine the partition for a given key
	- Issue is this stops our ability from doing efficient [[range queries]]
	- Keys that were adjacent are scattered across partitions and are no longer guaranteed sort ordering
	- In extreme cases where all reads and writes are for the same key we can end up routing to the same [[Partitions]]
		- Ie a celebrity with million of followers on a social media site
		- Nowadays most data systems can't automatically compensate for hot spot problems, onus is on the application to reduce the skew
			- [[Hot Spot Remedy]]
	- Becomes more complicated when [[Secondary Index]]s become to be involved
- [[Cassandra]] Partitioning Schema
	- Compromises between two partitioning strategies
	- Table in Cassandra can be declared with a [[compound primary key]] consisting of several columns
	- Only first part of the key is hashed to determine the partition
	- Other columns are used as an concatenated [[Index]] for sorting the data in Cassandaras [[SSTable]]
	- Stops a query for searching for a range of values within the first column but if it specifies a fixed value for the first column it can perform an efficient range scan based on other columns  of the keys
		- ie search by fixed (user_id, update_timestamp)
			- allows for range sort order of update_timestamp while fixing on a specific partiion of the user_id
			- Different users are stored on different partitions

## Details

## Conclusion


Type :: #topic
Links :: [[Computer Science]] [[System Design]] [[Partitioning]]
Creator ::
Date ::  2024-06-07 13:05