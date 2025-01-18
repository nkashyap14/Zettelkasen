# Edit Distance

#### Problem statement

You are given two strings `word1` and `word2`, each consisting of lowercase English letters.

You are allowed to perform three operations on `word1` an unlimited number of times:

- Insert a character at any position
- Delete a character at any position
- Replace a character at any position

Return the minimum number of operations to make `word1` equal `word2`.
##### Example 1
```
Input: word1 = "monkeys", word2 = "money"

Output: 2
```
##### Example 2
```
Input: word1 = "neatcdee", word2 = "neetcode"

Output: 3
```
#### Solution
```
class Solution:
    def minDistance(self, word1: str, word2: str) -> int:
        dp = [[float('inf')] * (len(word2) + 1) for _ in range(len(word1) + 1)]

        for j in range(len(word2) + 1):
            dp[-1][j] = len(word2) - j

        for i in range(len(word1) + 1):
            dp[i][-1] = len(word1) - i
  
        for i in range(len(word1) - 1, -1, -1):
            for j in range(len(word2) - 1, -1 , -1):
                if word1[i] == word2[j]:
                    dp[i][j] = dp[i + 1][j + 1]
                else:
                    #delete, replace, and insert
                    dp[i][j] = min(dp[i + 1][j], dp[i + 1][j + 1], dp[i][j + 1]) + 1

        return dp[0][0
```

###### Programming Language Utilized:

- [[Python]]
###### Data structure utilized:

- [[2D Dynamic Programming]]
#### Important Subdetails

#### Runtime of Optimal Solution

- O(m * n) space and run complexity where m is length of string 1 and n is length of string 2
---
Links :: [[#Example Code]] [[Computer Science]] [[Neetcode 150]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2025-01-14 15:36
