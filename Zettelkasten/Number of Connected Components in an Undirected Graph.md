# Number of Connected Components in an Undirected Graph

#### Problem statement

There is an undirected graph with `n` nodes. There is also an `edges` array, where `edges[i] = [a, b]` means that there is an edge between node `a` and node `b` in the graph.

The nodes are numbered from `0` to `n - 1`.

Return the total number of connected components in that graph.
##### Example 1
```
Input:
n=3
edges=[[0,1], [0,2]]

Output:
1
```
##### Example 2
```
Input:
n=6
edges=[[0,1], [1,2], [2,3], [4,5]]

Output:
2
```
#### Solution
```
class Solution:
    def countComponents(self, n: int, edges: List[List[int]]) -> int:
        adj = [[] for _ in range(n)]
        seen = set()

        for a, b in edges:
            adj[a].append(b)
            adj[b].append(a)

        def traverseComponent(n, seen, prev):
            if n in seen:
                return
            seen.add(n)
            
            for neighbor in adj[n]:
                if neighbor == prev:
                    continue
                traverseComponent(neighbor, seen, n)
        res = 0
        for n in range(n):
            if n not in seen:
                traverseComponent(n, seen, -1)
                res += 1
        return res
```

#### Solution 2: Union Find
```
class Solution:
    def countComponents(self, n: int, edges: List[List[int]]) -> int:
	    par = [i for i in range(n)]
	    rank = [1] * n


		def find(n1):
			res = n1
			while res != par[res]:
				#set parent = to the parent's parent aka grand parent
				#this is path compression that leads to time complexity of ackerman function
				par[res] = par[par[res]]
				res = par[res]

			return res

		def union(n1, n2):
			p1, p2 = find(n1), find(n2)

			if p1 == p2:
				return 0

			#the component that becomes the root parent depends on the rank's
			if rank[p2] > p1:
				par[p1] = p2
				rank[p2] += rank[p1]

			else:
				par[p2] = p1
				rank[p1] += rank[p2]

			return 1

		res = n
		for n1, n2 in edges:
			#each time you union components you decrement the number of components by one
			res -= union(n1, n2)

		return res
```

###### Programming Language Utilized:

- [[Python]]
###### Data structure utilized:

- [[Graph]]
- [[depth first search]]
- [[Union Find]]
#### Important Subdetails

#### Runtime of Optimal Solution

- O(V + E)
- O(V + E)
---
Links :: [[#Example Code]] [[Computer Science]] [[Neetcode 150]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-12-05 05:02
