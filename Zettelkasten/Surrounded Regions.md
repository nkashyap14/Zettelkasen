# Surrounded Regions

#### Problem statement

You are given a 2-D matrix `board` containing `'X'` and `'O'` characters.

If a continous, four-directionally connected group of `'O'`s is surrounded by `'X'`s, it is considered to be **surrounded**.

Change all **surrounded** regions of `'O'`s to `'X'`s and do so **in-place** by modifying the input board.
##### Example 1
```
Input: board = [
  ["X","X","X","X"],
  ["X","O","O","X"],
  ["X","O","O","X"],
  ["X","X","X","O"]
]

Output: [
  ["X","X","X","X"],
  ["X","X","X","X"],
  ["X","X","X","X"],
  ["X","X","X","O"]
]
```
#### Solution
```
class Solution:
    def solve(self, board: List[List[str]]) -> None:
        ROWS, COLS = len(board), len(board[0])
        def dfs(r, c):
            if r not in range(ROWS) or c not in range(COLS) or board[r][c] != "O":
                return
            board[r][c] = 'T'
            dire = [(0,1), (0, -1), (1, 0), (-1, 0)]
            for x, j in dire:
                dfs(r + x, c + j)

        for i in range(ROWS):
            for j in range(COLS):
                if board[i][j] == "O" and (i in [0, ROWS - 1] or j in [0, COLS - 1]):
                    dfs(i, j)

        for i in range(ROWS):
            for j in range(COLS):
                if board[i][j] == "O":
                    board[i][j] = "X"
        for i in range(ROWS):
            for j in range(COLS):
                if board[i][j] == "T":
                    board[i][j] = "O"
```

###### Programming Language Utilized:

- [[Python]]
###### Data structure utilized:

- [[Depth First Search]]
#### Important Subdetails

- The important trick to this problem is that the problem states to make all surrounded regions into X's and keep all non surrounded regions. Non surrounded regions can be said to be ones that have a border tile with them. As such this solution trick just changes the non surrounded regions into T's and then loops through the whole matrix graph and changes all remaining O's to T's as we know they are surrounded
- First thing we need to do is find all borderr tiles that are O. From there run a dfs on them in the four possible directions to find all O tiles that are said to be connected to them. THe dfs changes all of them to T's
- From there we can simply loop over all tiles and change all the O's to X's. Then one final loop over all needs to be done where we change all T's to O's.

#### Runtime of Optimal Solution
- O(mn) where m is rows and n is columns
---
Links :: [[#Example Code]] [[Computer Science]] [[Neetcode 150]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-10-20 17:30
