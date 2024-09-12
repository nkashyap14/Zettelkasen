# socket

- An interface that creates a two way channel between [[process|processes]] communicating on different devices
- Requires:
	- [[IP]] address + [[port]] number
		- together known as a [[socket endpoint]]
- The [[transport layer]] [[protocol]] is responsibel for exchanging data between processes
	- [[TCP]] / [[UDP]]
- 5 tuple info on a machine usually identifies a [[socket address | connection]]
	- Source IP
	- Source Port
	- Destination IP
	- Destination Port
	- Transport layer protocol
- Popular API technologies such as [[REST]], [[GraphQL]], and [[gRPC]] all at the most basic level use socket interfaces for [[process]] identification, connection establishment, and [[interprocess communication]]
- Socket Types:
	- [[Stream Socket]]s
	- [[Datagram Socket]]s
- Socket [[API]]:
	- [[socket function C|socket()]]
	- [[bind function C|bind()]]
		- associates a [[buffer]] with the [[file descriptor | socket descriptor]] and gives it a unique local name
	- [[listen function C|listen()]]
	- [[Connect Function C|connect()]]
	- [[Accept function C|accept()]]
	- [[send function C |send()]]
	- [[recv function C |recv()]]
	- close()
---
Links :: [[Computer Science]] [[Networking]] [[System Design]] [[API]]
Reference :: [[Unix Network Programming Volume 1]]
Type :: #atom
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-04-02 12:53
