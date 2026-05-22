# Components of DNS


- [[Name Server]]: DNS servers that respond to user queries
- [[Resource Records (DNS)]]: The smallest unit of information that user requests from the name servers. There are a few different types of Resource records including but not limited to:
	- [[A record (DNS)]]:
		- Maps a hostname to an ip address
		- Ex:   (A, relay1.main.educative.io,104.18.2.119)
	- [[NS record (DNS)]]:
		- Provides the hostname that is the authoritative DNS for a domain name
		- Ex: (NS, educative.io, dns.educative.io)
	- [[CNAME record (DNS)]]: 
		- Provides the mapping from alias to a canonical hostname
		- (CNAME, educative.io, server1.primary.educative.io)
	- Other types that might be worth learning in free time
		- [[SRV record (DNS)]]
- [[Cache|Caching]]
	- Domain Name system uses caching at different levels to reduce request latency for the end user
	- Caching plays an important role in reducing the burden on DNS infrastructure because it services requests of the entire internet
- Hierarchy:
	- DNS names servers are in a hierarchical form which allows it to be highly scalable because of its increasing size and query load
---
Links :: [[Computer Science]] [[Domain Name System]] [[System Design]]
Reference ::
Type :: #atom
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2025-10-28 14:45
