# How a RPC Works

- Calling environment is paused
- Procedure parameters are sent over the network to the environment where the procedure is to be executed
![[Pasted image 20251023174108.png]]

- Client, client stub and a RPC runtime run on client machine
- Server, Server stub, and RPC runtime run on server machine
- Steps that occur
	- Client initiates a client stub process by giving parameters as normal
		- Client stub is stored in address space of client
	- Client stub converts the parameters into a standardized format and packs them into a message
	- Client stub requests the local rpc runtime to deliver the message to the server
	- RPC runtime at client delivers message to the server. Then waits for message results to the server
	- Server rpc runtime receives message and passes it to server stub
	- Server stub unpacks the message takes the parameters out of it and calls the desired server routine to do the required execution
	- Server routine executes. Result is returned to server stub. Server stub packs the returned result into a message and sends it to the prc runtime at the server on the transport layer
	- Server runtime sends packed result to the client rpc runtime
	- Client rpc runtime receives the result and sends it to the client result to unpack
	- Execution process returns back to the client
---
Topics :: [[System Design]]
Reference ::
Type :: #molecule
Creator ::
Rating ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2025-10-23 17:40

