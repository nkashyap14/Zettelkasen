# Rotting Fruit

#### Problem statement

You are given a 2-D matrix `grid`. Each cell can have one of three possible values:

- `0` representing an empty cell
- `1` representing a fresh fruit
- `2` representing a rotten fruit

Every minute, if a fresh fruit is horizontally or vertically adjacent to a rotten fruit, then the fresh fruit also becomes rotten.

Return the minimum number of minutes that must elapse until there are zero fresh fruits remaining. If this state is impossible within the grid, return `-1`.
##### Example 1
```
Input: grid = [[1,1,0],[0,1,1],[0,1,2]]

Output: 4
```
##### Example 2
```
Input: grid = [[1,0,1],[0,2,0],[1,0,1]]

Output: -1
```
#### Solution
```
class Solution:
    def orangesRotting(self, grid: List[List[int]]) -> int:
        q = deque()
        fresh = 0

        for i in range(len(grid)):
            for j in range(len(grid[0])):
                if grid[i][j] == 2:
                    q.append((i, j))
                if grid[i][j] == 1:
                    fresh += 1

        m = 0
        dire = [(0, 1), (0, -1), (1, 0), (-1, 0)]
        while fresh > 0 and q:
                length = len(q)
                for x in range(length):
                    i, j = q.popleft()
                    for r, c in dire:
                        if ((i + r) in range(len(grid)) and (j + c) in range(len(grid[0])) and grid[i + r][j + c] == 1):
                            grid[i + r][j + c] = 2
                            q.append((i + r, j + c))
                            fresh -= 1
                m += 1

  

        return m if fresh == 0 else -1
```

###### Programming Language Utilized:

- [[Python]]
###### Data structure utilized:

- [[queue]]
- [[Breadth First Search]]
#### Important Subdetails

- Calculate the number of fruit needed to be turned rotten. This is a stopping condition
- Run a breadth first search with the starting points being the rotten fruits because they affect other fruits
- Only add cells to the queue if they contain fruit because only they can be affected by rotten fruit and then can pass the curse on
- Set up the deque, then if we want to iterate per minute over all the fruit we can just use the length of the q and then iterate over that range in an inner for loop
	- Only need to iterate over the new fruit that have been turned rotten because those are the only ones at each new minute that have new territory they can turn rotten
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
Date :: 2024-10-14 08:07
