# Fault Tolerance

- Fault tolerance refers to a [[Distributed System]] ability to execute persistently even if one or more of its components fail
- Two key qualities of fault tolerance
	- [[Availability]]
		- Ensures that the system remains accessible and can receive client requests at any time
	- [[reliability]]
		- Ensures that the system consistently processes these requests and performs the correct action every time
- Common techniques for fault tolerance
	- [[Replication|Replication Based Fault Tolerance]]
		- Allows us to swap out failed nodes with healthy ones, or a failed data store with its replica
		- Copies need to be updated regularly for [[Consistency Models]|consistency]
	- [[Checkpointing]]
		- A technique that saves the system's state in stable storage for later retrieval in case of failures due to errors or service disruptions
		- Two types of checkpointing:
			- Consistent state: A state is consistent in which all the individual processes of a system have a consistent view of the shared state or sequence of events that have occurred in a system
				- Criteria for consistent state:
					- All updates to data that were completed before the checkpoint are saved
					- Checkpoints include all the messages sent or received up until the checkpoint. No messages are in transit
					- Relationships and dependencies between system components and their states match normal operation
			- Inconsistent state:
				- A state where there are discrepancies in the saved states of different processes of a system

---
Links :: [[Computer Science]] [[System Design]]
Reference ::
Type :: #atom
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2025-10-24 01:50
