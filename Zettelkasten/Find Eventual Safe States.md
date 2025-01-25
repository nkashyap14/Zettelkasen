# Find Eventual Safe States

#### Problem statement

There is a directed graph of `n` nodes with each node labeled from `0` to `n - 1`. The graph is represented by a **0-indexed** 2D integer array `graph` where `graph[i]` is an integer array of nodes adjacent to node `i`, meaning there is an edge from node `i` to each node in `graph[i]`.

A node is a **terminal node** if there are no outgoing edges. A node is a **safe node** if every possible path starting from that node leads to a **terminal node** (or another safe node).

Return _an array containing all the **safe nodes** of the graph_. The answer should be sorted in **ascending** order.
##### Example 1
```
**Input:** graph = [[1,2],[2,3],[5],[0],[5],[],[]]
**Output:** [2,4,5,6]
**Explanation:** The given graph is shown above.
Nodes 5 and 6 are terminal nodes as there are no outgoing edges from either of them.
Every path starting at nodes 2, 4, 5, and 6 all lead to either node 5 or 6.
```
##### Example 2
```
**Input:** graph = [[1,2,3,4],[1,2],[3,4],[0,4],[]]
**Output:** [4]
**Explanation:**
Only node 4 is a terminal node, and every path starting at node 4 leads to node 4.
```
#### Solution: DFS with Cycle Detection
```
class Solution(object):
    def eventualSafeNodes(self, graph):
        """
        :type graph: List[List[int]]
        :rtype: List[int]
        """
        
        n = len(graph)

        adj = {i : [] for i in range(n)}

        for src in range(n):
            for node in graph[src]:
                adj[src].append(node)

        safe, visiting = set(), set()

        def dfs(i):
            if i in safe or not adj[i]:
                return True

            if i in visiting:
                return False

            visiting.add(i)
            for nei in adj[i]:
                #if a neighbor is unsafe then we know this is not a safe node either
                if not dfs(nei):
                    return False


			#we know a node is safe now that we have verified all its outgoing edges lead to safe/terminal nodes so add it to the safe set
            safe.add(i)

            return True

        res = []

        for i in range(n):
            if dfs(i):
                res.append(i)
  

        return res
```

#### Solution 2: Topological Sort

```
class Solution(object):
    def eventualSafeNodes(self, graph):

        n = len(graph)
        outdegree = [len(nodes) for nodes in graph]
        rev_graph = [[] for _ in range(n)]
        queue = []

        # Build reverse graph
        for i in range(n):
            for node in graph[i]:
                rev_graph[node].append(i)

            if outdegree[i] == 0:  # Terminal nodes
                queue.append(i)

        safe = []
        while queue:
            node = queue.pop(0)
            safe.append(node)
            for prev in rev_graph[node]:
                outdegree[prev] -= 1
                if outdegree[prev] == 0:
                    queue.append(prev)

        return sorted(safe)
```
###### Programming Language Utilized:

- [[Python]]
###### Data structure utilized:

- [[Topological Sort]]
- [[depth first search]]
- [[Graph]]
#### Important Subdetails

#### Runtime of Optimal Solution

- O(V + E) where v is vertexes and e is outgoing edges
- O(v) space complexity
- Topological sort solution is better
---
Links :: [[#Example Code]] [[Computer Science]] [[Leetcode Daily Contests]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2025-01-23 21:09
