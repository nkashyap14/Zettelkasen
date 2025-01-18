# Network Delay

#### Problem statement

You are given a network of `n` directed nodes, labeled from `1` to `n`. You are also given `times`, a list of directed edges where `times[i] = (ui, vi, ti)`.

- `ui` is the source node (an integer from `1` to `n`)
- `vi` is the target node (an integer from `1` to `n`)
- `ti` is the time it takes for a signal to travel from the source to the target node (an integer greater than or equal to `0`).

You are also given an integer `k`, representing the node that we will send a signal from.

Return the **minimum** time it takes for all of the `n` nodes to receive the signal. If it is impossible for all the nodes to receive the signal, return `-1` instead.
##### Example 1
```
Input: times = [[1,2,1],[2,3,1],[1,4,4],[3,4,1]], n = 4, k = 1

Output: 3
```
##### Example 2
```
Input: times = [[1,2,1],[2,3,1]], n = 3, k = 2

Output: -1
```
#### Solution
```
class Solution:
    def networkDelayTime(self, times: List[List[int]], n: int, k: int) -> int:
        adj = defaultdict(list)

        for src, dest, time in times:
            adj[src].append((dest, time)
  

        minHeap = [(0, k)]
        visit = set()

        t = 0

        while minHeap:
            w1, n1 = heapq.heappop(minHeap)
            #want to only use the nodes neighbor if we are at the shortest path to that node
            if n1 in visit:
                continue

            visit.add(n1)
            t = max(t, w1)

            for n2, w2 in adj[n1]:
                if n2 not in visit:
                    heapq.heappush(minHeap, (w1 + w2, n2))

        return t if len(visit) == n else -1
```

###### Programming Language Utilized:

-  [[Python]]
###### Data structure utilized:

- [[Djikstra's Shortest Path Algorithm]]
#### Important Subdetails

#### Runtime of Optimal Solution

- O(E * logV) where e is edges and V is verticeis
---
Links :: [[#Example Code]] [[Computer Science]] [[Neetcode 150]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2025-01-14 15:54
