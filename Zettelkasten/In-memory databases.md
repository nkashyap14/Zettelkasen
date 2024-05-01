# In-memory databases

 - As ram becomes cheaper cost per gigabyte argument of main memory limited use has gone down
 - led to development of in memory databases as some datasets can be stored entirely in [[RAM]]
 - Some like [[Memcached]] are intended for caching use where data can be lost if a machine is restarted
 - Ones where state is aimed to be stored can be utilized by writing periodic snapshots to disk or replicating in memory to state
 - When restarted needs to reload its state either from disk or over network from a replica
 - Performance advantage is because they can avoid the overheads of encoding in memory data structures in a form that can be written to disk, not because they don't need ot read from the disk
---
Links :: [[Computer Science]] [[Database]]
Reference :: [[Designing Data Intensive Applications]]
Type :: #atom
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-04-26 14:55
