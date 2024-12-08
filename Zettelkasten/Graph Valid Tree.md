# Graph Valid Tree

#### Problem statement

Given `n` nodes labeled from `0` to `n - 1` and a list of **undirected** edges (each edge is a pair of nodes), write a function to check whether these edges make up a valid tree.
##### Example 1
```
Input:
n = 5
edges = [[0, 1], [0, 2], [0, 3], [1, 4]]

Output:
true
```
##### Example 2
```
Input:
n = 5
edges = [[0, 1], [1, 2], [2, 3], [1, 3], [1, 4]]

Output:
false
```
#### Solution
```
class Solution:
    def validTree(self, n: int, edges: List[List[int]]) -> bool:
        if not n:
            return True

        adj = [[] for _ in range(n)]
  
        for a, b in edges:
            adj[a].append(b)
            adj[b].append(a)

        seen = set()

        def cycle(n, seen, prev):
            if n in seen:
                return False
            seen.add(n)
            for neighbor in adj[n]:
                if neighbor == prev:
                    continue
                if not cycle(neighbor, seen, n):
                    return False
            return True

        return cycle(0, seen, -1) and len(seen) == n
```

###### Programming Language Utilized:

- [[Python]]
###### Data structure utilized:

- [[depth first search]]
- [[Cycle detection]]
#### Important Subdetails

- Because this is an undirected graph we need to keep track of the previous node to make sure we don't jump to that via an edge and then detect a false positive cycle

#### Runtime of Optimal Solution

- O(V + E) runtime
- O(V + E) space complexity
---
Links :: [[#Example Code]] [[Computer Science]] [[Neetcode 150]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-12-05 04:52
