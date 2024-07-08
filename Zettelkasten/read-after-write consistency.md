# read-after-write consistency

- Guarantee that after a user reloads a page in an application after performing a write they will always see any updates they submitted themselves
	- Makes no promises about the writes of other users
- Implementation Techniques:
	- When reading something that a user may have modified read it from the leader otherwise a follower
		- Requires a way of knowing whether something has been modified without querying it
	- If most things are editable by a user previous approach wouldn't work as it would mean reading regularly from the leader and negating the benefit of [[Read-scaling Architecture]]
		- Can track time of last update, ie until 1 min after last update all reads from leader
		- Can monitor replication lag on followers and prevent queries on followers some x behjind
	- Client can remember timestamp of its most recent write
		- System can ensure the replica serving any reads for that user reflects updates till that timestamp
			- If replica doesnt reflect it use another replica or block query till replica has been caught up 
---
Links :: [[Computer Science]] [[System Design]] [[consistency]]
Reference ::
Type :: #atom
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-06-01 14:02
