# Longest Increasing Path in Matrix

#### Problem statement
You are given a 2-D grid of integers `matrix`, where each integer is greater than or equal to `0`.

Return the length of the longest strictly increasing path within `matrix`.

From each cell within the path, you can move either horizontally or vertically. You **may not** move **diagonally**.

##### Example 1
```
Input: matrix = [[1,2,3],[2,1,4],[7,6,5]]

Output: 7
```
#### Solution
```
class Solution:
    def longestIncreasingPath(self, matrix: List[List[int]]) -> int:
        ROWS, COLS = len(matrix), len(matrix[0])

        dp = {} #(r, c) -> Longest increasing path starting at r, c
        
        def dfs(r, c, prevVal):
            if (r < 0 or r == ROWS or
            c < 0 or c == COLS or 
            matrix[r][c] <= prevVal):
                return 0

            if (r, c) in dp:
                return dp[(r, c)]

            res = 1
            res = max(res, 1 + dfs(r + 1, c, matrix[r][c]))
            res = max(res, 1 + dfs(r - 1, c, matrix[r][c]))
            res = max(res, 1 + dfs(r, c + 1, matrix[r][c]))
            res = max(res, 1 + dfs(r, c - 1, matrix[r][c]))

            dp[(r, c)] = res
            return res

        for r in range(ROWS):
            for c in range(COLS):
                dfs(r, c, -1)

        return max(dp.values())
```

###### Programming Language Utilized:

- [[Python]]
###### Data structure utilized:

- [[2D Dynamic Programming]]
#### Important Subdetails

#### Runtime of Optimal Solution

- O(m * n) rutniem and space compleixty where m is rows and n is columns
---
Links :: [[#Example Code]] [[Computer Science]] [[Neetcode 150]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2025-02-07 12:56
