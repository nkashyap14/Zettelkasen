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
- Done via version values from the response back
- Client writes the newer value back to the replica
- Works well for values that are frequently read
## Anti-entropy process
- Some datastores have a background [[process]] that constantly looks for differences in the data between replicas and copies missing data from one replica to another
- Without this process values that are rarely read may be missing from some replicas and thusly have reduced [[Durability]] because read repair is only performed when a value is read by the application

## [[Leaderless Quorums]]
- Leaderless quorums allow for increased fault tolerance without need for failover + allows for databases with leaderless replications to be appealing for high availability and low latency use cases

## [[Sloppy Quorum]]
- Network interruption can cut a client off from large number of db nodes which are still alive.
	- So r or w reachable nodes do not remain
- Decision becomes should it be better to return errors for all requests or to accept writes anyways and write them to some nodes that are reachable
	- idea is that a large cluster may have more than n nodes (see [[Partitioning]]) but only n nodes for the data you are writing. may have more nodes available to you accessible but just not the n nodes you need to write to. in that case you write to the neighbors
		- still requires w, r successful responses but may include nodes that are not among the designated n home nodes for a value
		- writes sent to that one node are temporarily accepted and then are sent to the appropriate home nodes. Called [[hinted handoff]]
	- second part is known as a sloppy quorum
- Used to increase write availability as long as any w nodes are available the database can accept writes
	- also means that when w + r > n cant be sure to read the last value for a key as the latest value may have been temporarily written to some nodes outside of n
- Is an assurance of durability
	- that the data is stored on w nodes somewhere but no guarantee that a read of r nodes will see it until hinted handoff is done
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