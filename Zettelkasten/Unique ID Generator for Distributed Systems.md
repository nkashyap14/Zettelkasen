# Unique ID Generator for Distributed Systems

### Idea 1: Auto Increment
- Utilize a [[relational database]]'s auto increment feature on a single machine
- Not viable in distributed envrionments
### Idea 2: [[Multimaster Replication]]
- Utilize auto increment alongside muliple databases
- Increment by k where k = number of database servers
- Downsides
	- Hard to scale across multiple data centers
	- ID's do not go up with time across servers
	- Hard to scale once server is removed or added
### Idea 3: [[UUID|Universally Unique Identifier]]
- 128 [[bits|bit]] number used to identify info in computer systems
- Low probability of collision. Can generate 1 billion uuid's ever second for 100 years than the probability of a single duplicate is 50%
- Can generate independently across web servers
- Cons:
	- 128 bit might be above requirements which could be 64 bit
	- ID's do not go up with time
	- Could be non numeric
### Idea 4: [[Ticket Server]]
- Developed by flickr to generate distributed [[primary key|primary keys]]
- Idea revolves around using a centralized auto_increment field in a single database server
- Pro:
	- Numeric id's
	- Easy to implement for small -> medium scale
- Con:
	- Singlepoint of failure with the ticket server
	- If there are multiple ticket servers than that introduces data synchronization issues
### Idea 5: [[Twitter Snowflake]]
---
Links :: [[Computer Science]] [[System Design]] [[Design Pattern]][[Distributed System]]
Reference :: [[Alex Xu System Design Volume 2]]
Type :: #atom
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-04-03 16:42
