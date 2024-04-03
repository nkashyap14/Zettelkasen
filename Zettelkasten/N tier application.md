# N tier application

- An application or [[distributed system]] with more than 3 components in its architecture
- Components include:
	- [[Cache]]
	- [[Message Queues]] for asynchronous behavior
	- [[Load Balancers]]
	- [[Search Servers]] for searching through massive amounts of data
	- [[Microservices]]
- Typical Web Application Architecture:
	1. Messaging Server:
	   - Communicates with: Backend Server
	2. Backend Server:
	   - Communicates with:
	     a. UI on Client Side
	     b. Messaging Server
	     c. Cache Server
	3. Cache Server:
	   - Sits between: Backend Server and Database Server
	   - Communicates with:
	     a. Backend Server
	     b. Database Server
	4. Database Server:
	   - Receives communications from: Cache Server


---
Links :: [[Computer Science]] [[System Design]]
Reference ::
Type :: #atom
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-04-02 00:44
