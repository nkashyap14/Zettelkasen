# Data Flow Via Databases

- Process that writes to a database encodes data
- Process that reads from a database decodes data
- When a value is written by a newer version of the code but decoded by older code it can be that newer fields that are added in are not unpacked and handled correctly by older code
	- have to make sure to handle correctly
- Data outlives code:
	- When we deploy new versions of applications may entirely replace code base. database contents however do not change very frequently. Observation is that data outlives code
- Can take snapshots of data base from time to time for backup purposes
---
Links :: [[Computer Science]] [[System Design]]
Reference :: [[Designing Data Intensive Applications]] [[Modes of Data Flow]]
Type :: #atom
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-05-21 08:30
