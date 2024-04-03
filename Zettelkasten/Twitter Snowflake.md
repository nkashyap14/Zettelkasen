# Twitter Snowflake

- Utilized for the problem of [[Unique ID Generator for Distributed Systems|UUID Generation]]
- Divides an id into different sections of bits
- Sign bit: 1 [[bits|bit]]
	- Always 0
	- Reserved for future use
- Timestamp: 41 bits
	- Represents milliseconds since epoch or custom epoch
	- Allows us to sort by time as timestamps grow
- Datacenter ID: 5 bits
	- 2^5 options or 32 machines per data center
- Sequence number: 12 bits
	- For every id generated this number is incremented by 1
	- Rests to 0 every millisecond
	- Allows each machine to generate 2^12 = 4096 new id's per millisecond


---
Links :: [[Computer Science]] [[Twitter]] [[Design pattern]]
Reference :: [[Alex Xu System Design Volume 2]]
Type :: #atom
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-04-03 17:00
