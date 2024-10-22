# Graph Database

- Type of data model where data is modeled as a graph
- If many-to-many relationships are very common in the data then it becomes natural to start modeling data as a graph
- Good for evolving data, as you add features to the application a graph can easily be extended to accommodate changes in your applications data structure
- 2 types of objects:
	- Vertices: Also known as
		- Node
		- Entity
	- Edges: Also Known as
		- relationship
		- arc
	- Types of data that can be modeled as a graph:
		- Social Graph
			- Nodes are people, edges indicate relationships
		- Web graph
			- vertices are web pages, edges indicating html links to other pages
		- Road or rail networks
			- vertices are junctions and edges representing the roads or railway lines between them
- Two types of Graph Models for structuring and querying data in graphs:
	- Property Graph model:
		- Vertex consists of:
			- Unique identifier
			- Set of outgoing edges
			- Set of incoming edges
			- Collection of properties (key value pairs)
		- Edge consists of:
			- Unique identifier
			- Vertex which edge starts (tail vertex)
			- Vertex at which edge ends (head vertex)
			- Label to describe the relationship between the two vertexes
			- Collection of properties (key value pairs)
		- Can think of the graph store as consisting of two relational tables, one for vertices, and one for edges
	- [[Triple-Store]]

---
Links :: [[Computer Science]] [[Data Models]] [[Database]]
Reference ::
Type :: #atom
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-04-21 12:14
