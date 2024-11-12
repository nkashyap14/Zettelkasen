# Data warehouse

- Separate database that analysts can query to their heart's content without affecting [[OLTP]] operations that may be powering systems facing customers
- Contains a read-only copy of the data in all the various OLTP systems in the company
- Process of getting data into the warehouse is known as [[ETL|Extract-Transform-Load]]
- Most commonly utilizes a [[relational database|relational data model]] because [[SQL]] is a good fit for analytical queries
- Usually utilized in a formulaic style known as [[Star Schema]] or also called dimensional modeling
- [[Materialized Aggregates]]
- Advantage is that the data warehouse can be optimized for analytic access patterns while not affecting [[OLTP]] operations 
- Fact tables can grow extremely large with trillions of rows and perhaps even [[petabytes]] of data
	- Storing and querying them efficiently becomes a problem
	- Typical query only accesses 4/5 columns at a time
	- leads to the idea of needing [[Column-Oriented Storage]]
---
Links :: [[Computer Science]] [[System Design]]
Reference :: [[Designing Data Intensive Applications]]
Type :: #atom
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-04-26 15:42
