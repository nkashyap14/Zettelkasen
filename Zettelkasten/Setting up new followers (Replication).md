# Setting up new followers (Replication)

1. Take a consistent snapshot of the leader’s database at some point in time — if possible, without taking a lock on the entire database. Most databases have this feature, as it is also required for backups. In some cases, third-party tools are needed, such as innobackupex for MySQL [8]. 
2. Copy the snapshot to the new follower node. 
3. The follower connects to the leader, and requests all data changes that happened since the snapshot was taken. This requires that the snapshot is associated with an exact position in the leader’s replication log. That position has various different names: for example, PostgreSQL calls it log sequence number, and MySQL calls it binlog coordinates.
4. When the follower has processed the backlog of data changes since the snapshot, we say it has caught up. It can now continue to process data changes from the leader as they happen
---
Links :: [[Computer Science]] [[Replication]] [[System Design]]
Reference :: [[Designing Data Intensive Applications]]
Type :: #atom
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-05-31 15:17
