# Pacific Atlantic Water Flow

#### Problem statement

You are given a rectangular island `heights` where `heights[r][c]` represents the **height above sea level** of the cell at coordinate `(r, c)`.

The islands borders the **Pacific Ocean** from the top and left sides, and borders the **Atlantic Ocean** from the bottom and right sides.

Water can flow in **four directions** (up, down, left, or right) from a cell to a neighboring cell with **height equal or lower**. Water can also flow into the ocean from cells adjacent to the ocean.

Find all cells where water can flow from that cell to **both** the Pacific and Atlantic oceans. Return it as a **2D list** where each element is a list `[r, c]` representing the row and column of the cell. You may return the answer in **any order**.
##### Example 1
```
Input: heights = [
  [4,2,7,3,4],
  [7,4,6,4,7],
  [6,3,5,3,6]
]

Output: [[0,2],[0,4],[1,0],[1,1],[1,2],[1,3],[1,4],[2,0]]
```
##### Example 2
```
Input: heights = [[1],[1]]

Output: [[0,0],[0,1]]
```
#### Solution
```
class Solution:
    def pacificAtlantic(self, heights: List[List[int]]) -> List[List[int]]:
        ROWS, COLS = len(heights), len(heights[0])
        pac, atl = set(), set()
  
        def dfs(r, c, visit, prevHeight):
            if r not in range(ROWS) or c not in range(COLS) or (r, c) in visit or heights[r][c] < prevHeight:
                return

            visit.add((r, c))
            dire = [(0, 1), (0, -1), (1, 0), (-1, 0)]
  
            for i, j in dire:
                dfs(r + i, c + j, visit, heights[r][c])

        for i in range(COLS):
            dfs(0, i, pac, heights[0][i])
            dfs(ROWS - 1, i, atl, heights[ROWS - 1][i])

        for i in range(ROWS):
            dfs(i, 0, pac, heights[i][0])
            dfs(i, COLS - 1, atl, heights[i][COLS - 1])

        res = []
        for r in range(ROWS):
            for c in range(COLS):
                if (r, c) in atl and (r, c) in pac:
                    res.append([r, c])

        return res
```

###### Programming Language Utilized:
- [[Python]]
###### Data structure utilized:

- [[depth first search]]
- [[Set]]
#### Important Subdetails

- Because we are seeing what points can reach both the pacific and the atlantic we need two sets
- We can run a dfs on each point checking if it can reach the atlantic, and if it can reach the pacific
	- The dfs is run on points that we know can reach the pacific/atlantic aka the border points
	- From there the dfs set just visits and adds all points that are reachable from those border points to the set
	- This populates a set of points that can reach the pacific and the atlatnic as two separate sets
	- From there we just iterate through the list of all possible points and add the ones that are in both sets to the result array
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
Date :: 2024-10-14 09:35
