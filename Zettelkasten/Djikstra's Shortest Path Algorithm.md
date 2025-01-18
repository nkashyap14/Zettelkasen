# Djikstra's Shortest Path Algorithm

## Summary

- Single source node shortest path algorithm for  a weighted [[Graph]]
	- Aka will output the shortest path to all other connected node from one specific source node
- Applies to minimization problems
	- These are optimization problems
	- Can be solved using [[greedy|greedy method]]
	- Has predefined procedures for getting shortest path in a graph 
- V = vertices
- Worst case runtime is O(V^2) for the case of a fully connected graph
## Pseudocode

- Pick a source node
- Initialize distances to all nodes, initially source node distance is 0 all other nodes are infinity
- The node gets put into a priority queue/minheap which prioritizes by distance/weight of connections
- Each time you pop the cheapest node in terms of distance / weight that you haven't visited. you calculate its total distance with the edge and if its less than the current distance set in the graph you update the shortest distance seen
	- this is called relaxation

## Python Implementation


```
class Graph:
   def __init__(self, graph: dict = {}):
       self.graph = graph  # A dictionary for the adjacency list

   def add_edge(self, node1, node2, weight):
       if node1 not in self.graph:  # Check if the node is already added
           self.graph[node1] = {}  # If not, create the node
       self.graph[node1][node2] = weight  # Else, add a connection to its neighbor

	def shortest_distances(self, source: str):

		distances = {node: float("inf") for node in self.graph}
		distances[source] = 0

		#initilaize a priority queue aka a minheap in python
		pq = [(0, source)]
		heapq.heapify(pq)

		visited = set()

		while pq:
			curr_distance, curr_node = heapq.heappop(pq)

			#have already visited and found its shortest path
			if curr_node in visited:
				continue

			visited.add(curr_node)

			#graph[node] points to a dictionary which maps its neighbors + weights
			for neighbor, weight in self.graph[current_node].items()
				tentative_distance = current_distance + weight
				if tentative_distance < distances[neighbor]:
					distances[neighbor] = tentative_distance
					heapq.heappush(pq, (tentative_distance, neighbor))

		return distances
```

## Problems that use it

- [[Network Delay]]

Type :: #topic
Links :: [[Computer Science]]
Creator ::
Date ::  2025-01-14 16:43