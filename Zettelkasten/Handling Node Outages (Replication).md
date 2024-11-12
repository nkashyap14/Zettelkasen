# Handling Node Outages (Replication)

- Follower failure:
	- Catch up recovery
	- On local disk each follower keeps a [[log]] of the data changes it has received from the leader
	- If a follower crashes + restarts, or if network is interrupted follower recovers via the log by using the last processed transaction + then connects to leader and requests all data changes from that point
		- Allows it to catch up to leader and then continue receiving a stream of data changes
- Leader failure:
	- Follower needs to be promoted to a new leader
	- Clients need to be reconfigured to send new writes to new leader
	- Followers need to consume from new leader
	- Process is called [[failover]]
		- can occur manually or automatically
		- [[Automatic Failover]]
- These techniques are for single-leader replication
---
Links :: [[Computer Science]] [[System Design]] [[Shared-Nothing Architecture]] [[Replication]] [[Single-Leader]]
Reference :: [[Designing Data Intensive Applications]]
Type :: #atom
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-05-31 15:18
