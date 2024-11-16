# Palindrome Partitioning

#### Problem statement

Given a string `s`, split `s` into substrings where every substring is a palindrome. Return all possible lists of palindromic substrings.

You may return the solution in **any order**.
##### Example 1
```
Input: s = "aab"

Output: [["a","a","b"],["aa","b"]]
```
##### Example 2
```
Input: s = "a"

Output: [["a"]]
```
#### Solution
```
class Solution:
    def partition(self, s: str) -> List[List[str]]:
        res = []
        part = []

        def dfs(i):
            if i >= len(s):
                res.append(part.copy())
                return
            for j in range(i, len(s)):
                if self.isPali(s, i, j):
                    part.append(s[i: j + 1])
                    dfs(j + 1)
                    part.pop()

        dfs(0)
        return res

    def isPali(self, s, l, r):
        while l < r:
            if s[l] != s[r]:
                return False
            l, r = l + 1, r - 1
        return True
```

###### Programming Language Utilized:

- [[Python]]
###### Data structure utilized:

- [[Backtracking]]
#### Important Subdetails

- Need to check every possible partition to see if its a possible palindrome and then add those to the list and ultimately add the list over to the result array when its outside index
#### Runtime of Optimal Solution

- Runtime: O(n * 2^n), 2 choices for n elements and on each of those n elements might do a copy in the worst case which is why we multiply by n 
- Space complexity: O(n)
---
Links :: [[#Example Code]] [[Computer Science]] [[Neetcode 150]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-11-13 10:32
