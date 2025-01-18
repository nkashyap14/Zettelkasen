# Unique Paths II

#### Problem statement

You are given an `m x n` integer array `grid`. There is a robot initially located at the **top-left corner** (i.e., `grid[0][0]`). The robot tries to move to the **bottom-right corner** (i.e., `grid[m - 1][n - 1]`). The robot can only move either down or right at any point in time.

An obstacle and space are marked as `1` or `0` respectively in `grid`. A path that the robot takes cannot include **any** square that is an obstacle.

Return _the number of possible unique paths that the robot can take to reach the bottom-right corner_.

The testcases are generated so that the answer will be less than or equal to `2 * 109`.
##### Example 1
```
**Input:** obstacleGrid = [[0,0,0],[0,1,0],[0,0,0]]
**Output:** 2
**Explanation:** There is one obstacle in the middle of the 3x3 grid above.
There are two ways to reach the bottom-right corner:
1. Right -> Right -> Down -> Down
2. Down -> Down -> Right -> Right
```
##### Example 2
```
**Input:** obstacleGrid = [[0,1],[0,0]]
**Output:** 1
```
#### Solution : Bottom up using input grid
```
class Solution(object):
    def uniquePathsWithObstacles(self, obstacleGrid):
        """
        :type obstacleGrid: List[List[int]]
        :rtype: int
        """

        m, n = len(obstacleGrid), len(obstacleGrid[0])

		#if starting space is a rock no movement available so 0
        if obstacleGrid[0][0] == 1:
            return 0

		#1 way to go from starting cell to current cel
        obstacleGrid[0][0] = 1

		#changing dp array so that each cell's value is going to be = to the number of paths to that cell from the starting cell

		#setting base case. all cells in first row and first column have only one path to them from starting cell
		#go right or go down
        for i in range(1, m):
	        #if the cell is a rock than 0 ways to it
            if obstacleGrid[i][0] == 1:
                obstacleGrid[i][0] = 0
            else:
	            #path to this space depends on a path being available to preivous space
                obstacleGrid[i][0] = obstacleGrid[i - 1][0]

  
		#same process initilaizing the first row
        for j in range(1, n):
            if obstacleGrid[0][j] == 1:
                obstacleGrid[0][j] = 0
            else:
                obstacleGrid[0][j] = obstacleGrid[0][j - 1]

        #go through eveyr cell, don't have to touch first row/column so go 1, 1
        #each cell's total number of ways is = the sum of the ways to the cell above it and the cell to the left of it
        #if the cell is a orkc than 0 ways
        for i in range(1, m):
            for j in range(1, n):
                if obstacleGrid[i][j] == 0:
                    obstacleGrid[i][j] = obstacleGrid[i - 1][j] + obstacleGrid[i][j - 1]
                else:
                    obstacleGrid[i][j] = 0


        return obstacleGrid[m - 1][n - 1]
```


#### Solution 2: DFS with Memoization

```
class Solution(object):
    def uniquePathsWithObstacles(self, obstacleGrid):
        """
        :type obstacleGrid: List[List[int]]
        :rtype: int
        """

        memo = {}
        m, n = len(obstacleGrid), len(obstacleGrid[0])
        #returns number of ways to reach m - 1, n - 1 from i, j
        def dfs(i, j):
            if (i, j) in memo:
                return memo[(i, j)]

            if (i, j) == (m - 1, n - 1):
                memo[(i, j)] = 1 if obstacleGrid[m - 1][n - 1] == 0 else 0
                return memo[(i, j)]

            if i == m or j == n or obstacleGrid[i][j] == 1:
                return 0
        
            memo[(i, j)] = dfs(i + 1, j) + dfs(i, j + 1)

            return memo[(i, j)]

        return dfs(0, 0)

```
###### Programming Language Utilized:

- [[Python]]
###### Data structure utilized:

- [[2D Dynamic Programming]]
#### Important Subdetails

- Both dynamic programming solutions available are shown
#### Runtime of Optimal Solution

- O(m, n) space complexity and O(m, n) runtime
- Bottom up solution has O(1) space as we only use the input array
---
Links :: [[#Example Code]] [[Computer Science]] [[Leetcode Problem]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2025-01-15 11:19
