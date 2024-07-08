# Problems with Replication Lag

## Reading Your Own Writes

- If user wants to view data shortly after making a write the new data may not have yet reached the replica
	- to the user it may look as though the data was lost
	- For these situations we need [[read-after-write consistency]]
## Monotonic Reads

- When reading from asynchronous followers possible for a user to see things moving backwards in time
	- if user makes several reads from different replicas
	- Later reads are observing the system at an earlier point in time than the first query
- Monotonic reads is a guarantee that this anomaly doesn't happen
	- [[Monotonic consistency]]
	- Lesser guarantee that [[strong consistency]]
	- Stronger guarantee than [[Eventual Consistency]]
	- Means that if a user makes several reads in sequence they will not see time go backwards aka not read older data after having read newer data 
- One way to achieve this is to make sure each user always makes reads from the same replica

## Consistent Prefix Reads

- Concerns violation of causality
- [[Consistent Prefix Reads]]
- Guarantees that if a sequence of writes happen in a certain order anyone reading them will see those writes in the same order
- Particular issue with [[sharded databases]]
	- In distributed databases [[Partitioning|partitions]] operate independently so nno global ordering of writes 
		- Can make the writes causally related to each other
## Converging towards consistent state
- In [[Multi-Leader]] configuration no defined ordering of writes so can end up with inconsistent states
- Want to converge towards a consistent state aka all replicas arrive at the same final value when all changes have been replicated
- Mechanisms to achieve this:
	- Give each write a unique id and pick the write with the highest id as the winner and throw away other writes
		- [[Last Write Wins]]
	- Give each replica a unique id and let writes originating at a higher number replica take precedence
		- Implies [[data loss]]

---
Links :: [[Computer Science]] [[System Design]] [[Replication Lag]] [[Replication]]
Reference :: [[Designing Data Intensive Applications]]
Type :: #atom
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-06-01 13:56
