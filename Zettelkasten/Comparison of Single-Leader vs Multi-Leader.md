## Performance
- Every write must go over internet to datacenter with the leader in single leader
	- Adds latency to writes
- In multi-leader every write can be processed in the local data center and replicated asynchronously
## Fault Tolerance
- Increased in multi-leader as cross datacenter replication increases overall system [[Availability]]
- In single leader If data center with leader fails [[failover]] can kick in and promote a follower in another datacenter to be a leader
## Network Fault Tolerance
- Increased tolerance of network problems in multi leader setup
---
Links :: [[Computer Science]] [[Algorithm]] [[Replication Algorithm's]] [[Single-Leader]] [[Multi-Leader]] [[System Design]]
Reference :: [[Designing Data Intensive Applications]]
Type :: #atom
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-05-31 15:08