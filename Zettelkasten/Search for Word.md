# Search for Word

#### Problem statement

Given a 2-D grid of characters `board` and a string `word`, return `true` if the word is present in the grid, otherwise return `false`.

For the word to be present it must be possible to form it with a path in the board with horizontally or vertically neighboring cells. The same cell may not be used more than once in a word.
##### Example 1
```
Input: 
board = [
  ["A","B","C","D"],
  ["S","A","A","T"],
  ["A","C","A","E"]
],
word = "CAT"

Output: true
```
##### Example 2
```
Input: 
board = [
  ["A","B","C","D"],
  ["S","A","A","T"],
  ["A","C","A","E"]
],
word = "BAT"

Output: false
```
#### Solution
```
class Solution:
    def exist(self, board: List[List[str]], word: str) -> bool:
        dire = [(0, 1), (0, -1), (1, 0), (-1 , 0)]
        ROWS, COLS = len(board), len(board[0])
        seen = set()
        def dfs(i, j, index):
            if index == len(word):
                return True

            if i not in range(ROWS) or j not in range(COLS) or (i, j) in seen or word[index] != board[i][j]:
                return False

            res = False
            seen.add((i, j))

            for x, y in dire:
                res = res or dfs(i + x, j + y, index + 1)
            seen.remove((i, j))

            return res

        for i in range(ROWS):
            for j in range(COLS):
                if board[i][j] == word[0]:
                    if dfs(i, j, 0):
                        return True

        return False
```

###### Programming Language Utilized:

- [[Python]]
###### Data structure utilized:

- [[Backtracking]]
#### Important Subdetails

#### Runtime of Optimal Solution

- Runtime: O(n * m * dfs) = O(n * m * 4^len(word))
	- 4 ^ len(word) because each recursion time we have 4 branches and we go to a depth of the lenght of the word
	- n * m because we iterate over all cells of the board in the worst case
---
Links :: [[#Example Code]] [[Computer Science]] [[Neetcode 150]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-11-13 09:57
