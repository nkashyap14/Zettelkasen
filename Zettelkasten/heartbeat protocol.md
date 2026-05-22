# heartbeat protocol

- A mechanism that helps us detect failures in a distributed system. If there is a central server all servers periodically send a heartbeat message to it to show that they are alive and functioning
- If there is no central server all servers randomly select a subset and send that subset a heartbeat message every few seconds.
- If no heartbeats are sent in a while that is an indication to a [[Distributed System]] that there might be a failure or a crash on those nodes

---
Links :: [[Computer Science]] [[System Design]]
Reference ::
Type :: #atom
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2025-10-23 16:53
