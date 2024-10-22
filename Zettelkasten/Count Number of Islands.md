# Count Number of Islands

#### Problem statement

Given a 2D grid `grid` where `'1'` represents land and `'0'` represents water, count and return the number of islands.

An **island** is formed by connecting adjacent lands horizontally or vertically and is surrounded by water. You may assume water is surrounding the grid (i.e., all the edges are water).
##### Example 1
```
Input: grid = [
    ["0","1","1","1","0"],
    ["0","1","0","1","0"],
    ["1","1","0","0","0"],
    ["0","0","0","0","0"]
  ]
Output: 1
```
##### Example 2
```
Input: grid = [
    ["1","1","0","0","1"],
    ["1","1","0","0","1"],
    ["0","0","1","0","0"],
    ["0","0","0","1","1"]
  ]
Output: 4
```
#### Solution
```
class Solution:
    def numIslands(self, grid: List[List[str]]) -> int:
        def navigateIsland(grid, x, y, seen):
            if x not in range(len(grid)) or y not in range(len(grid[0])) or grid[x][y] == '0' or (x, y) in seen:
                return
            seen.add((x, y))
            dire = [[0, 1], [0, -1], [1, 0], [-1, 0]]
            for r, c in dire:
                navigateIsland(grid, x + r, y + c, seen)

        seen, res = set(), 0
        for i in range(len(grid)):
            for j in range(len(grid[0])):
                if (i, j) not in seen and grid[i][j] == "1":
                    res += 1
                    navigateIsland(grid, i, j, seen)

        return res
```

###### Programming Language Utilized:

- [[Python]]
###### Data structure utilized:

- [[Graph]]
- [[depth first search]]
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
Date :: 2024-10-08 19:33
