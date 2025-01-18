# Interleaving String

#### Problem statement

You are given three strings `s1`, `s2`, and `s3`. Return `true` if `s3` is formed by **interleaving** `s1` and `s2` together or `false` otherwise.

**Interleaving** two strings `s` and `t` is done by dividing `s` and `t` into `n` and `m` substrings respectively, where the following conditions are met

- `|n - m| <= 1`, i.e. the difference between the number of substrings of `s` and `t` is at most `1`.
- `s = s1 + s2 + ... + sn`
- `t = t1 + t2 + ... + tm`
- **Interleaving** `s` and `t` is `s1 + t1 + s2 + t2 + ...` or `t1 + s1 + t2 + s2 + ...`

You may assume that `s1`, `s2` and `s3` consist of lowercase English letters.
##### Example 1
```
Input: s1 = "aaaa", s2 = "bbbb", s3 = "aabbbbaa"

Output: true
```
##### Example 2
```
Input: s1 = "", s2 = "", s3 = ""

Output: true
```
#### Solution
```
class Solution:
    def isInterleave(self, s1: str, s2: str, s3: str) -> bool:
        memo = {}
        #a call to this dfs from i, j returns if you can make s3[i + j:] by interleaving strings s1, s2
        def dfs(i, j):

            if (i, j) in memo:
                return memo[(i, j)]

            if i + j == len(s3):
                memo[(i, j)] = (i == len(s1)) and (j == len(s2))
                return memo[(i, j)]
                
            ch = s3[i + j]

            if i < len(s1) and s1[i] == ch:
                if dfs(i + 1, j):
                    memo[(i, j)] = True
                    return memo[(i, j)]
    
            if j < len(s2) and s2[j] == ch:
                if dfs(i, j + 1):
                    memo[(i, j)] = True
                    return memo[(i, j)]
            
            memo[(i, j)] = False
            return memo[(i, j)]

        return dfs(0, 0)
```

###### Programming Language Utilized:

- [[Python]]
###### Data structure utilized:

- [[2D Dynamic Programming]]
#### Important Subdetails
#### Runtime of Optimal Solution

- O(m * n) run complexity and O(m * n) space complexity where m is lenght of s1 and n is length of s2
---
Links :: [[#Example Code]] [[Computer Science]] [[Neetcode 150]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2025-01-09 15:26
