# Data Flow via Asynchronous Message Passing

- Asynchronous message passage systems are similar to [[RPC]] in that a clien'ts request is delivered to another process with low latency
- Goes through an intermediary called a [[Message Queues|message broker]]
	- also refered to as message queue or message oriented middleware
	- Allows us to decouple the sender form the recipient
- Difference from RPC is that the message passing communication is one way, usually a reply isn't sent to the sender
- General flow:
	- [[process]] sends a message to a named [[queue]] or topic
	- [[Message Broker]] ensures that the message is delivered to one or more [[consumer]] or [[subscriber]]
	- Can be many producers or consumers to the same topic
	- Topic only provides one way data flow
---
Links :: [[Computer Science]] [[System Design]] [[Modes of Data Flow]]
Reference ::
Type :: #atom
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-05-21 08:34
