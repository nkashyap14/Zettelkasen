# Islands and Treasures

#### Problem statement
You are given a m×nm×n 2D `grid` initialized with these three possible values:

1. `-1` - A water cell that _can not_ be traversed.
2. `0` - A treasure chest.
3. `INF` - A land cell that _can_ be traversed. We use the integer `2^31 - 1 = 2147483647` to represent `INF`.

Fill each land cell with the distance to its nearest treasure chest. If a land cell cannot reach a treasure chest than the value should remain `INF`.

Assume the grid can only be traversed up, down, left, or right.

##### Example 1
```
Input: [
  [2147483647,-1,0,2147483647],
  [2147483647,2147483647,2147483647,-1],
  [2147483647,-1,2147483647,-1],
  [0,-1,2147483647,2147483647]
]

Output: [
  [3,-1,0,1],
  [2,2,1,-1],
  [1,-1,2,-1],
  [0,-1,3,4]
]

```
##### Example 2
```
Input: [
  [0,-1],
  [2147483647,2147483647]
]

Output: [
  [0,-1],
  [1,2]
]
```
#### Solution
```
class Solution:
    def islandsAndTreasure(self, grid: List[List[int]]) -> None:
        ROWS, COLS = len(grid), len(grid[0])
        seen = set()
        q = deque()

        def addRoom(r, c):
            if r < 0 or r == ROWS or c < 0 or c == COLS or (r, c) in seen or grid[r][c] == -1:
                return
            seen.add((r, c))
            q.append([r, c])

  

        for r in range(ROWS):
            for c in range(COLS):
                if grid[r][c] == 0:
                    q.append([r, c])
                    seen.add((r, c))

        dist = 0
        while q:
            for i in range(len(q)):
                r, c = q.popleft()
                grid[r][c] = dist
                for x, y in [(0, 1), (0, -1), (1, 0), (-1, 0)]:
                    addRoom(r + x, c + y)

            dist += 1
```

###### Programming Language Utilized:

- [[Python]]

###### Data structure utilized:

- [[Graph]]
- [[Breadth First Search]]
#### Important Subdetails

- Depth First search would run at O((mn)^2)
- This solution stems from the idea that we start at every room and then just do a breadth first search starting from there and mark each room reached at every level from there as distance with distance being incremented by 1 each time
- Don't add the room or tile  to the q and visited if its not in bounds or its marked as a dead end (-1) or we've already visited it because in that case we know its already been marked by its optimal value
#### Runtime of Optimal Solution

- O(mn) runtime
---
Links :: [[#Example Code]] [[Computer Science]] [[Neetcode 150]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-10-12 09:29
