# Document Database

- Type of database
- [[Mongodb]]
- Stores  documents
- Document reference acts a foreign key
- Allows for nested records
- Limitations:
	- Can not refer directly to a nested item within a document
	- Poor support for joins
	- Not appealing when need many to many relationships
	- Awkward for highly interconnected data
- Document databases are a type of non-relational ([[NoSQL]]) database designed to store, retrieve, and manage document-oriented information. These databases are optimized for storing semi-structured data as documents, typically in formats like [[JSON]], BSON, or [[XML]], which allows for a more flexible schema compared to traditional relational databases. 
- In document databases, each document is self-contained and represents a complex data object. The data within these documents can be nested, enabling the storage of hierarchical structures within a single record. This model facilitates direct mapping to objects in application code, making it especially popular among developers working on modern web applications, mobile applications, and real-time analytics.
- Target use cases where data comes in self-contained documents and relationships between one document and another are rare
---
Links :: [[Computer Science]] [[Database]]
Reference :: [[Designing Data Intensive Applications]]
Type :: #atom
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-04-19 17:25
