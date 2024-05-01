# Star Schema

- A type of schema
- At the center of this model is a fact table
- Each row of the fact table represents an event that occurred at a particular time
- Usually facts are captured as individual events but that can lead to large fact tables on the magnitude of petabytes for large corporate entitie
- Some of the columns in fact tables are attributes
- Some of the columns are [[foreign key]]s to other tables called dimension tables
- Dimension tables hold the who , what, where, when, how, and why of the events represented by a row
- Called star schema as a visualized representation of these relationships has the fact table in the middle with the foreign keys branching to dimension tables like rays of a star
- Variation of this table is known as a snowflake schema where dimensions are further broken into sub-deimnsions
---
Links :: [[Computer Science]] [[Data warehouse]]
Reference :: [[Designing Data Intensive Applications]]
Type :: #atom
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-04-26 15:42
