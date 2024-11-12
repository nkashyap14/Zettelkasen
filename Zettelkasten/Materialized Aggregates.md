# Materialized Aggregates

- Data warehouse queries often involve an aggregate function like COUNT, SUM, MIN etc
- Can be wasteful to crunch raw data through an aggregate every time if being reused every time 
- Can cache it by creating a [[Materialized View]] which is defined like a standard [[view]] the difference being that the materialized view is an actual copy of the query results written to disk while the virtual view is just a shortcut for writing queries.
	- When underlying data changes materialized view needs to be updated as it is a [[denormalized]] copy of the data
	- Database can automatically update that however such updates make writes expensive which is why its not necessarily great for [[OLTP]] databases
		- Better for read heavy data warehouses
- Another option for optimizing this queries are data cubes
	- N dimensions where each dimension is one of the dimension tables
	- Rows are compiled aggregates (SUM, AVG, COUNT, MIN etc) on the dimensions
	- Can simply scan across the rows to get compiled aggregate values across dimensions
	- Certain queries become very fast beacause they are precomputed

---
Links :: [[Computer Science]] [[Database]] [[Data warehouse]] [[Data Models]]
Reference :: [[Designing Data Intensive Applications]]
Type :: #atom
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-04-27 13:23
