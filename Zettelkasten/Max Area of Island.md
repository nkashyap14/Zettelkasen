# Max Area of Island

#### Problem statement

You are given a matrix `grid` where `grid[i]` is either a `0` (representing water) or `1` (representing land).

An island is defined as a group of `1`'s connected horizontally or vertically. You may assume all four edges of the grid are surrounded by water.

The **area** of an island is defined as the number of cells within the island.

Return the maximum **area** of an island in `grid`. If no island exists, return `0`.
##### Example 1
```
Input: grid = [
  [0,1,1,0,1],
  [1,0,1,0,1],
  [0,1,1,0,1],
  [0,1,0,0,1]
]

Output: 6
```

#### Solution
```
class Solution:
    def maxAreaOfIsland(self, grid: List[List[int]]) -> int:
        def dfs(grid, x, y, seen):
            if (x, y) in seen or x not in range(len(grid)) or y not in range(len(grid[0])) or grid[x][y] == 0:
                return 0
            seen.add((x, y))
            res = 1

            dire = [[0, 1],[0,-1],[1,0],[-1,0]]
            for r, c in dire:
                res += dfs(grid, x + r, y + c, seen)
            return res

        seen, res = set(), 0
        for x in range(len(grid)):
            for y in range(len(grid[0])):
                if grid[x][y] == 1 and grid[x][y] not in seen:
                    res = max(res, dfs(grid, x, y, seen))

        return res
```

###### Programming Language Utilized:

- [[Python]]
###### Data structure utilized:
- [[depth first search]]
- [[Graph]]
#### Important Subdetails

#### Runtime of Optimal Solution
---
Links :: [[#Example Code]] [[Computer Science]] [[Neetcode 150]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-10-08 20:13
