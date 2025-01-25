# Minimum Window Substring

#### Problem statement

Given two strings `s` and `t`, return the shortest **substring** of `s` such that every character in `t`, including duplicates, is present in the substring. If such a substring does not exist, return an empty string `""`.

You may assume that the correct output is always unique.
##### Example 1
```
Input: s = "OUZODYXAZV", t = "XYZ"

Output: "YXAZ"
```
##### Example 2
```
Input: s = "xyz", t = "xyz"

Output: "xyz"
```
#### Solution
```
class Solution:
    def minWindow(self, s: str, t: str) -> str:

        if t == "":
            return ""  

        countT, window = {}, {}

        for ch in t:
            countT[ch] = 1 + countT.get(ch, 0)

        have, need = 0, len(countT)
        res, resLen = [-1, -1], float("inf")
        l = 0

        for r in range(len(s)):
            c = s[r]
            window[c] = 1 + window.get(c, 0)

            if c in countT and window[c] == countT[c]:
                have += 1

            while have == need:
                if (r - l + 1) < resLen:
                    res = [l, r]
                    resLen = r - l + 1
                    
                window[s[l]] -= 1
                if s[l] in countT and window[s[l]] < countT[s[l]]:
                    have -= 1

                l += 1

        l, r = res
        return s[l : r + 1] if resLen != float("inf") else ""
```

###### Programming Language Utilized:

- [[Python]]
###### Data structure utilized:

- [[Sliding Window]]
#### Important Subdetails
- [[Leetcode Hard]]
#### Runtime of Optimal Solution

- O(n) runtime and O(m + n) space complexity where m and n are the lenght of the strings
---
Links :: [[#Example Code]] [[Computer Science]] [[Neetcode 150]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2025-01-21 11:27
