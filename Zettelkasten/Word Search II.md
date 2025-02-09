# Word Search II

#### Problem statement

Given a 2-D grid of characters `board` and a list of strings `words`, return all words that are present in the grid.

For a word to be present it must be possible to form the word with a path in the board with horizontally or vertically neighboring cells. The same cell may not be used more than once in a word.
##### Example 1
```
Input:
board = [
  ["a","b","c","d"],
  ["s","a","a","t"],
  ["a","c","k","e"],
  ["a","c","d","n"]
],
words = ["bat","cat","back","backend","stack"]

Output: ["cat","back","backend"]

```

##### Example 2
```
Input:
board = [
  ["x","o"],
  ["x","o"]
],
words = ["xoxo"]

Output: []
```
#### Solution
```
class TrieNode:
    def __init__(self):
        self.children = {}
        self.isWord = False

    def addWord(self, word):
        cur = self
        for c in word:
            if c not in cur.children:
                cur.children[c] = TrieNode()
            cur = cur.children[c]
        cur.isWord = True

class Solution:
    def findWords(self, board: List[List[str]], words: List[str]) -> List[str]:
        root = TrieNode()
        for w in words:
            root.addWord(w)

        ROWS, COLS = len(board), len(board[0])
        res, visit = set(), set()

        def dfs(r, c, node, word):
            #base case
            if r < 0 or c < 0 or r == ROWS or c == COLS or (r, c) in visit or board[r][c] not in node.children:
                return

            visit.add((r, c))
            node = node.children[board[r][c]]

            word += board[r][c]
            if node.isWord:
                res.add(word)


            dfs(r + 1, c, node, word)
            dfs(r - 1, c, node, word)
            dfs(r, c + 1, node, word)
            dfs(r, c - 1, node, word)

            #remvoe from visiting as this is backtracking
            visit.remove((r, c))

        for r in range(ROWS):
            for c in range(COLS):
                dfs(r, c, root, "")


        return list(res)
```

###### Programming Language Utilized:

- [[Python]]
###### Data structure utilized:

- [[Trie]]
#### Important Subdetails

- Using a trie node is what makes or breaks this problem
#### Runtime of Optimal Solution

- Time complexity is O(m * n * 4 * 3^t - 1 + s)
	- Where m is rows
	- n is columns
	- t is the maximum length of any word in the array words
	- and s is the sum of the length of all the words
- Space complexity is O(s) as we are building out a trie
---
Links :: [[#Example Code]] [[Computer Science]] [[Neetcode 150]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2025-02-01 17:12
