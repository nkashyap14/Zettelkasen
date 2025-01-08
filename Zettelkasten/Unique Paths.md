# Unique Paths

#### Problem statement

There is an `m x n` grid where you are allowed to move either down or to the right at any point in time.

Given the two integers `m` and `n`, return the number of possible unique paths that can be taken from the top-left corner of the grid (`grid[0][0]`) to the bottom-right corner (`grid[m - 1][n - 1]`).

You may assume the output will fit in a **32-bit** integer.
##### Example 1
```
Input: m = 3, n = 6

Output: 21
```
##### Example 2
```
Input: m = 3, n = 3

Output: 6
```
#### Solution
```
class Solution:
    def uniquePaths(self, m: int, n: int) -> int:
        
        #doing n + 1 and m + 1 because at the last row or columnn theoeretically we can move right or down
        #they do but they get 0 ways because it is out of  bounds
        dp = [[0] * (n + 1) for _ in range(m + 1)]

        #base case aka from the goal there is one way to move
        dp[m - 1][n - 1] = 1

        for i in range(m - 1, -1, -1):
            for j in range(n - 1, -1, -1):
                #move down
                #move to the right are our two options
                #so assuming we have calculated those two ways optimal paths then all we
                #have to do is add those 2's
                dp[i][j] += dp[i + 1][j] + dp[i][j + 1]

  

        return dp[0][0]
```

#### Space Optimized

```
class Solution:
    def uniquePaths(self, m: int, n: int) -> int:
        #only can go right at the bottom row:
        #setting bottom row up now going up the rows calculating each row
        oldRow = [1] * n
        
        #m rows:
        #range goes m - 1
        #1 row calculated alreayd so for m = 3 we want to loop 2 times so range(m - 1)
        for i in range(m - 1):
            row = [1] * n
            #because we are going to use the right vlaue as well
            for j in range(n - 2, -1, -1):
                #current cells value is = down rows same index + value to the right
                #right most cell is always 1 because we know it can only go one direction! DOWN
                row[j] = oldRow[j] + row[ j + 1]
            oldRow = row
        #at the end our 0 value will have the total
        return row[0]
```
###### Programming Language Utilized:
- [[Python]]
###### Data structure utilized:

- [[2D Dynamic Programming]]
#### Important Subdetails

- Bottom up solution

#### Runtime of Optimal Solution

- O(m * n) runtime for both
- O(m * n) space complexity for non optimized O(n) space complexity for optimized as we only have two rows which is O(1) but O(n) space used
---
Links :: [[#Example Code]] [[Computer Science]] [[Neetcode 150]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2025-01-07 14:31
