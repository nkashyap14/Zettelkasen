# Regular Expression Matching

#### Problem statement

You are given an input string `s` consisting of lowercase english letters, and a pattern `p` consisting of lowercase english letters, as well as `'.'`, and `'*'` characters.

Return `true` if the pattern matches the **entire** input string, otherwise return `false`.

- `'.'` Matches any single character
- `'*'` Matches zero or more of the preceding element.
##### Example 1
```
Input: s = "aa", p = ".b"

Output: false

```
##### Example 2
```
Input: s = "nnn", p = "n*"

Output: true
```
#### Solution
```
class Solution:
    def isMatch(self, s: str, p: str) -> bool:
        
        cache = {}

        def dfs(i, j):
            if (i, j) in cache:
                return cache[(i, j)]

            if i >= len(s) and j >= len(p):
                return True

            if j >= len(p):
                return False

            match = i < len(s) and (s[i] == p[j] or p[j] == ".")

            if (j + 1) < len(p) and p[j + 1] == '*':
                #return if either of the two star matching scenaiors are true
                #dont use the star
                cache[(i, j)] =  (dfs(i, j + 2) or 
                (match and dfs(i + 1, j))) #if we have a match at current and we use the star
                return cache[(i, j)]

            if match:
                cache[(i, j)] =  dfs(i + 1, j + 1)
                return cache[(i, j)]

            cache[(i, j)] = False
            return cache[(i, j)]
        return dfs(0, 0)
```

###### Programming Language Utilized:

 - [[Python]]
###### Data structure utilized:

- [[2D Dynamic Programming]]
- [[Memoization]]
#### Important Subdetails

#### Runtime of Optimal Solution

- O(m * n) runtime and space complexity where n is length of string and m is length of pattern
---
Links :: [[#Example Code]] [[Computer Science]] [[Neetcode 150]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2025-02-10 14:37
