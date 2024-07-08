# failover

- Leader failure:
	- Follower needs to be promoted to a new leader
	- Clients need to be reconfigured to send new writes to new leader
	- Followers need to consume from new leader
- Things that can go wrong:
	- If [[Asynchronous replication]] is in use than new leader may not have received all the writes from the old leader before it failed
		- if former leader rejoins post new leader being elected what happens to those writes
			- common strat is to discard but may violate durability expectations
	- [[split brain]]
		- where both nodes believe they are the leader and both leaders accept writes and there is no process for resolving conflicts
		- Leads to lost/corrupted data
	- Right timeout before declaring a leader dead 
		- If timeout is too short can lead to unnecessary failovers
			- iie temporary load spike that causes a nodes response time to increase
			- Network glitch that leads to delayed packets
---
Links :: [[Computer Science]] [[Replication]] [[Horizontal Scaling]] [[Node]]
Reference :: [[Designing Data Intensive Applications]]
Type :: #atom
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-05-31 15:22
