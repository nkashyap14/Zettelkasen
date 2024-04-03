# GraphQL

- [[Query Language]] for [[API|API's]]
- Allows for the fetching of data from multiple endpoints in a single request
- Enables the client to specify exactly what data it wants and eliminates problems like [[Overfetching]] and [[Underfetching]]
- Removes the [[Multiple Requests Problem]]
- Components:
	- [[GraphQL Server]] : Takes API's and exposes them to the client via ad endpoint
	- [[GraphQL Client]] : Accepts queries, connets to the endpoin, and issues queries to gather data
- Operations:
	- Queries: Used to fetch data
	- Mutations: Used to modify data on the server side
- Drawbacks:
	- Error handling: Requires parsing the response, increasing complexity and [[latency]]
	- File uploading: Must be implemented by developer
	- [[Cache|Web caching]]: More complex as need to work with multiple endpoints
	- Requires additional round trips inside the data center to different components

---
Links :: [[Computer Science]]
Reference ::
Type :: #atom
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-04-03 17:50
