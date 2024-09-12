- Leader filled replication is based on the idea that a client sends a write request to one node (leader) and db takes care of propagation
	- Leader determines the order in which writes are processed
- Some storage systems allow any replica to accept writes
- [[Dynamodb]] is leaderless
	- [[Cassandra]] is leaderless replication model db
- In some implementations client directly sends its writes to replicas
- In other implementations a [[coordinator node]] does it
	- Coordinator node does not enforce an ordering of writes
## Writing to the database when node  is down
- No [[failover]] in a leaderless system
- Write is sent to down node it simply misses it client ignores that one of the replicas misses the write
- When down node comes back up its data is stale. To solve the problem when a client reads from the db it sends its request to multiple replicas/nodes and gets various values. A [[version number]] is used to determine the newer value
## [[Read Repair]]
- When a client reads from several nodes in parallel it can detect stale values
## Anti-entropy process
- Some datastores have a background [[process]] that constantly looks for differences in the data between replicas and copies missing data from one replica to another

## [[Leaderless Quorums]]
- Leaderless quorums allow for increased fault tolerance without need for failover + allows for databases with leaderless replications to be appealing for high availability and low latency use cases

## [[Sloppy Quorum]]
- Network interruption can cut a client off from large number of db nodes which are still alive.
	- So r or w reachable nodes do not remain
- Decision becomes should it be better to return errors for all requests or to accept writes anyways and write them to some nodes that are reachable
	- second part is known as a sloppy quorum
- Used to increase write availability as long as any w nodes are available the database can accept writes
	- also means that when w + r > n cant be sure to read the last value for a key as the latest value may have been temporarily written to some nodes outside of n
---
Links :: [[Computer Science]] [[Algorithm]] [[Replication Algorithm's]] [[Replication]] [[System Design]]
Reference :: [[Designing Data Intensive Applications]]
Type :: #atom
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-05-31 15:08