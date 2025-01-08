# Word Break

#### Problem statement

Given a string `s` and a dictionary of strings `wordDict`, return `true` if `s` can be segmented into a space-separated sequence of dictionary words.

You are allowed to reuse words in the dictionary an unlimited number of times. You may assume all dictionary words are unique.
##### Example 1
```
Input: s = "neetcode", wordDict = ["neet","code"]

Output: true
```
##### Example 2
```
Input: s = "applepenapple", wordDict = ["apple","pen","ape"]

Output: true
```
#### Solution
```
class Solution:
    def wordBreak(self, s: str, wordDict: List[str]) -> bool:

        dp = [False] * (len(s) + 1)
        dp[len(s)] = True


        for i in range(len(s) - 1, -1 , -1):
            for w in wordDict:
                if (i + len(w)) <= len(s) and s[i: i + len(w)] == w:
                    dp[i] = dp[i + len(w)]
                if dp[i]:
                    break
        return dp[0]
```

###### Programming Language Utilized:

- [[Python]]
###### Data structure utilized:

- [[Dynamic Programming]]
#### Important Subdetails

#### Runtime of Optimal Solution

- O(m * n * t) where m is the number of words, t is the max lenght of a word, and n is the length of the string
---
Links :: [[#Example Code]] [[Computer Science]] [[Neetcode 150]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2025-01-02 13:49
