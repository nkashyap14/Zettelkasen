- Use different log formats for replication + for [[Storage Engine]]
- Allows replication log to be decoupled from the storage engine internals
- Sometimes called a [[logical log]] to distinguish it from storage engine's physical data representation
- usually a sequence of records describing writes to the database tables at the granularity of a row
	- For inserted row log contains new values of all columns
	- For deleted rows enough information to uniquely identify row that was deleted (typically [[primary key]])
	- For an updated row just enough information to uniquely idnetify the updated row and the new values of all columns that changed
---
Links :: [[Computer Science]] [[Implementation of Replication Logs]] [[Replication]] [[System Design]]
Reference :: [[Designing Data Intensive Applications]]
Type :: #atom
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-05-31 15:29
