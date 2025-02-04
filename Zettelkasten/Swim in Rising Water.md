# Swim in Rising Water

#### Problem statement

You are given a square 2-D matrix of distinct integers `grid` where each integer `grid[i][j]` represents the elevation at position `(i, j)`.

Rain starts to fall at time = `0`, which causes the water level to rise. At time `t`, the water level across the entire grid is `t`.

You may swim either horizontally or vertically in the grid between two adjacent squares if the original elevation of both squares is less than or equal to the water level at time `t`.

Starting from the top left square `(0, 0)`, return the minimum amount of time it will take until it is possible to reach the bottom right square `(n - 1, n - 1)`.
##### Example 1
```
Input: grid = [[0,1],[2,3]]

Output: 3
```
##### Example 2
```
Input: grid = [
  [0,1,2,10],
  [9,14,4,13],
  [12,3,8,15],
  [11,5,7,6]]
]

Output: 8
```
#### Solution
```
class Solution:
    def swimInWater(self, grid: List[List[int]]) -> int:
        N = len(grid)
        visit = set()

        minH = [[grid[0][0], 0, 0]] #maxheight, r, c

        directions = [[0, 1],[1, 0], [-1, 0], [0, -1]]

        while minH:
            t, r, c = heapq.heappop(minH)

            if r == N - 1 and c == N - 1:
                return t

            for dr, dc in directions:
                neiR, neiC = r + dr, c + dc

                if (neiR < 0 or neiC < 0 or neiR == N or neiC == N or (neiR, neiC) in visit):
                    continue

                visit.add((neiR, neiC))
                heapq.heappush(minH, (max(t, grid[neiR][neiC]), neiR, neiC))
```

###### Programming Language Utilized:

- [[Python]]
###### Data structure utilized:

- [[Djikstra's Shortest Path Algorithm]]
	- modified. the path cost we are counting is  the max height seen so far
#### Important Subdetails

#### Runtime of Optimal Solution
- Time complexity O(n^2 log n)
- Space complexity O(n^2)
---
Links :: [[#Example Code]] [[Computer Science]] [[Neetcode 150]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2025-02-04 12:55
