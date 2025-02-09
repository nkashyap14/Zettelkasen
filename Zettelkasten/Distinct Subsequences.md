# Distinct Subsequences

#### Problem statement

You are given two strings `s` and `t`, both consisting of english letters.

Return the number of distinct **subsequences** of `s` which are equal to `t`.
##### Example 1
```
Input: s = "caaat", t = "cat"

Output: 3
```
##### Example 2
```
Input: s = "xxyxy", t = "xy"

Output: 5

- (x)x(y)xy
- (x)xyx(y)
- x(x)(y)xy
- x(x)yx(y)
- xxy(x)(y)
```
#### Solution
```
class Solution:
    def numDistinct(self, s: str, t: str) -> int:
        memo = {}

        def dfs(i, j):
            if j == len(t):
                return 1
            
            if i == len(s):
                return 0

            if (i, j) in memo:
                return memo[(i, j)]

            if s[i] == t[j]:
                #if characters match check the ways when we match the current
                #characters and when we choose not to match the current chars
                memo[(i, j)] = dfs(i + 1, j + 1) + dfs(i + 1, j)
            else:
                memo[(i, j)] = dfs(i + 1, j)

            return memo[(i, j)]
        return dfs(0, 0)
```

###### Programming Language Utilized:

- [[Python]]
###### Data structure utilized:

- [[2D Dynamic Programming]]
#### Important Subdetails

#### Runtime of Optimal Solution

- O(m*n) runtime and space complexity where m is length of string 1 and n is length of string 2
---
Links :: [[#Example Code]] [[Computer Science]] [[Neetcode 150]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2025-02-07 12:55
