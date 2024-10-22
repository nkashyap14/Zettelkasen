# Longest Substring Without Repeating Characters

#### Problem statement

Given a string `s`, find the _length of the longest substring_ without duplicate characters.

A **substring** is a contiguous sequence of characters within a string.
##### Example 1
```
Input: s = "zxyzxyz"
Output: 3
```
##### Example 2
```
Input: s = "xxxx"
Output: 1
```
#### Solution
```
class Solution:
    def lengthOfLongestSubstring(self, s: str) -> int:
        l, r = 0, 0
        seen = set()
        res = 0
        for r in range(len(s)):
            if s[r] in seen:
                while s[r] in seen:
                    seen.remove(s[l])
                    l += 1
            seen.add(s[r])
            res = max(res, r - l + 1)

		return res
```

###### Programming Language Utilized:

- [[Python]]
###### Data structure utilized:

- [[Sliding Window]]
#### Important Subdetails

#### Runtime of Optimal Solution

- O(n) solution despite the nested loop. The reason is the nested loop doesnt run n times but rather will run at max O(n) times total not per iteration of the loop as max we will only remove n characters from the set and only add n characters from the set. The constant simplifies and we get O(n)
- Space complexity: O(n) as the set can get big but the sliding window solution is O(1)
---
Links :: [[#Example Code]] [[Computer Science]] [[Neetcode 150]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-10-04 16:31
