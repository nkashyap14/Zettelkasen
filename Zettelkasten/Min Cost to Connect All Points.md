# Min Cost to Connect All Points

#### Problem statement

You are given a 2-D integer array `points`, where `points[i] = [xi, yi]`. Each `points[i]` represents a distinct point on a 2-D plane.

The cost of connecting two points `[xi, yi]` and `[xj, yj]` is the **manhattan distance** between the two points, i.e. `|xi - xj| + |yi - yj|`.

Return the minimum cost to connect all points together, such that there exists exactly one path between each pair of points.
##### Example 1
```
Input: points = [[0,0],[2,2],[3,3],[2,4],[4,2]]

Output: 10
```
#### Solution
```
class Solution:
    def minCostConnectPoints(self, points: List[List[int]]) -> int:
        def manhattanDistance(x1, y1, x2, y2):
            return abs(x1 - x2) + abs(y1 - y2)

        adj = defaultdict(list)
        for i, point in enumerate(points):
            x, y = point[0], point[1]
            for j in range(i + 1, len(points)):
                dist = manhattanDistance(x, y, points[j][0], points[j][1])
                adj[i].append((dist, j))
                adj[j].append((dist, i))


        res = 0
        visit = set()
        minH = [[0, 0]]

        while len(visit) < len(points):
            cost, point = heapq.heappop(minH)
            if point in visit:
                continue
            res += cost
            visit.add(point)
            for neiCost, visitPoint in adj[point]:
                if visitPoint not in visit:
                    heapq.heappush(minH, [neiCost, visitPoint])

        return res
```

###### Programming Language Utilized:

- [[Python]]
###### Data structure utilized:

- [[Prim's Algorithm]]
#### Important Subdetails

#### Runtime of Optimal Solution

- Time complexity: O(n^2 * log⁡n)
- Space complexity: O(n^2)
---
Links :: [[#Example Code]] [[Computer Science]] [[Neetcode 150]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2025-01-15 14:26
