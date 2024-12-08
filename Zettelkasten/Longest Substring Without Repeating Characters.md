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
        max_length = left = 0
        count = {}
  
        for right, c in enumerate(s):
            count[c] = 1 + count.get(c, 0)
            while count[c] > 1:
                count[s[left]] -= 1
                left += 1
            max_length = max(max_length, right - left + 1)

        return max_length
```

###### Programming Language Utilized:

- [[Python]]
###### Data structure utilized:

- [[Sliding Window]]
#### Important Subdetails

- [[Hashmap]] solution with frequency counts is more efficient than using a set
#### Runtime of Optimal Solution

- O(n) solution despite the nested loop. The reason is the nested loop doesnt run n times but rather will run at max O(n) times total not per iteration of the loop as max we will only remove n characters from the set and only add n characters from the set. The constant simplifies and we get O(n)
- Space complexity: O(n) as the set can get big but the sliding window solution is O(1)
	- O(1) because there are a fixed amount of characters to be used
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
