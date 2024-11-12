# RPC

- Latest incarnation of long line of technologies for making [[API]] requests over a network
- Based on the idea of remote procedure call which has been around 1970's
- Makes a request to a remote network service look the same as calling a function or method in your programming language within the same process
	- called location transparency
- While convenient is fundamentally flawed
	- network requests are unpredictable as request response can get lost or remote machine may be slow
	- local functions return result or crash, network requests can time out
	- network requests are slower than a function call
	- need to encode and send data over the wire which can be difficult with larger objects
- Main use case of rpc frmameworks is on requests between services owned by the same organization in the same data center
- [[gRPC]]
- [[Finagle]]
- [[Rest.li]]
---
Links :: [[Computer Science]] [[System Design]]
Reference :: [[Designing Data Intensive Applications]]
Type :: #atom
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-05-21 08:38
