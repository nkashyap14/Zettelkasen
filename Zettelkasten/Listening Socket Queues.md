# Listening Socket Queues

- For a listening socket kernel maintains two queues
	- Incomplete connection queue which contains an entry for each SYN that has arrived from a client for which the server is awaiting completing of the [[Three Way Handshake]]
	- Completed connection queue with an entry for each client with which the connection is established

![[SocketQueues.jpg]]
- When the process calls accept the first entry on the completed queue is returned to the process or put to sleep if the queue is empty until an entry is placed on the completed queue
---
Topics :: [[Listen Function C]] [[socket]] [[Three Way Handshake]]
Reference :: [[Unix Network Programming Volume 1]]
Type :: #atom
Creator ::
TAF ::
Discussion ::
Dis_Topic :: [[Computer Science]] [[Networking]]
Resolved ::
Date :: 2024-03-27 10:20
