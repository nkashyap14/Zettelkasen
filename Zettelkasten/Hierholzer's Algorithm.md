# Hierholzer's Algorithm

## Summary

- An algorithm used to find an [[Eulerian Path]] within a [[undirected graph]] or a [[directed graph]]
- Step 1 need to determine if there even exists an eulerian path
	- [[Conditions needed for an Eulerian Path or Circuit]]
- Find valid start node
	- the node with outdegree - indegree = 1 is the only valid start node as it is the one with an extra outgoing edge
	- Node with indegree - outdegree = 1 is the only valid end node as it is the one with an extra incoming edge
	- if all indegree = outdegree then any node with non zero degree is a valid start
## Pseudocode

- Variables:
	- n = number of vertices
	- m = number of edges in graph
	- g = adjacency list for graph
- indegree [0] * n
- outdgree [0] * n
- Path = empty integer linked list data structure

function findEulerianPath():
	countInDegreeOutDegree():
	 if not graphHasEulerianPath(): return null

	 dfs(findStartNode())

	if path.size() == m + 1: return path

	return null

function findStartNode():
	start = 0

	for i = 0; i < n; i += 1
			#if we have a unique starting node
		if out[i] - in[i] == 1: return i

			#can start at any node that has an outgoing edge
		 if out[i] > 0: start = i

	return start

function dfs(at):
	while(out[at] != 0):
		next_edge = g[at].get(--out[at])
		dfs(next_edge.to)

	path.insertFirst(at)
## Python Implementation

## Problems that use it


Type :: #algorithm 
Links :: [[Computer Science]] [[Graph Theory]]
Creator ::
Date ::  2025-01-14 16:43