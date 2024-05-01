# OLTP

- Online Transaction Processing
- Small number of records fetched per query as read pattern
- Random-access low latency writes from user input as write pattern
- Primarly used by end user/customer via a web app
- Data represents the latest state of data at current point in time
- Data size from gigabytes to terabytes
- Typically user facing so we see a huge volume of requests
- To handle load app's usually only touch a small number of records in each query
- Disk seek time is often the bottleneck here
- The storage engine uses an [[index]] to find the data for the requested key
- [[Storage Engine]] has two main types
	- [[log-structured]]
	- [[update-in-place]]

---
Links :: [[Computer Science]]
Reference :: [[Designing Data Intensive Applications]]
Type :: #atom
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-04-26 15:40
