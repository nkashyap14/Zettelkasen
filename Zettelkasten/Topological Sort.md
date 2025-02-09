# Topological Sort

## Summary

- Topological sorting is an algorithm used in [[directed graphs]] to arrange nodes such that for every directed edge from node `u` to node `v`, node `u` comes before `v`. This is a natural approach when dealing with dependencies, like in project scheduling, task ordering, or handling prerequisites.
- We start by calculating the indegree of each node, which tells us how many nodes depend on it. Nodes with an indegree of zero are independent and can be processed first, so we enqueue them. Then, using a queue, we dequeue nodes, process their neighbors, update the prerequisite lists, and enqueue any neighbors whose indegree drops to zero. This continues until we’ve processed all nodes, ensuring the correct order of traversal.
- Also known as [[Kahn's Algorithm]]
## Pseudocode

## Python Implementation

## Problems that use it

- [[Course Schedule IV]]


Type :: #algorithm 
Links :: [[Computer Science]]
Creator ::
Date ::  2025-01-14 16:43