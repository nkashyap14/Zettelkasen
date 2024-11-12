# Permutation String

#### Problem statement
You are given two strings `s1` and `s2`.

Return `true` if `s2` contains a permutation of `s1`, or `false` otherwise. That means if a permutation of `s1` exists as a substring of `s2`, then return `true`.

Both strings only contain lowercase letters.
##### Example 1
```
Input: s1 = "abc", s2 = "lecabee"

Output: true
```
##### Example 2
```
Input: s1 = "abc", s2 = "lecaabee"

Output: false
```
#### Solution 1
```
class Solution:
    def checkInclusion(self, s1: str, s2: str) -> bool:
	    if len(s1) > len(s2):
		    return False

		s1Count, s2Count = [0] * 26, [0] * 26

		for i in range(len(s1)):
			s1Count[ord(s1[i]) - ord('a')] += 1
			s2Count[ord(s2[i]) - ord('a')] += 1

		matches = 0
		for i in range(26):
			matches += (1 if s1Count[i] == s2Count[i] else 0)

		l = 0
		for r in range(len(s1), len(s2)):
			if matches == 26:
				return True
			index = ord(s2[r]) - ord('a')
			s2Count[index] += 1
			if s1Count[index] == s2Count[index]:
				matches += 1
			elif s1Count[index] + 1 == s2Count[index]:
				matches -= 1

			index = ord(s2[l]) - ord('a')
			s2Count[index] -= 1
			if s1Count[index] == s2Count[index]:
				matches += 1
			elif s2Count[index] + 1 == s1Count[index]:
				matches -= 1
			l += 1
		return matches == 26
```
#### Solution 2
```
class Solution:
    def checkInclusion(self, s1: str, s2: str) -> bool:
        if len(s1) > len(s2):
            return False

        count1 = {}
        for ch in s1:
            count1[ch] = count1.get(ch, 0) + 1

        l, r = 0, len(s1) - 1
        print("l : {}, r : {}".format(l, r))
        while r <= len(s2) - 1:
            count2 = {}
            for i in range(l, r + 1):
                count2[s2[i]] = count2.get(s2[i], 0) + 1
            print(count2)
            if count1 == count2:
                return True
            l += 1
            r += 1

        return False
```
###### Programming Language Utilized:

###### Data structure utilized:
#### Important Subdetails

#### Runtime of Optimal Solution

- O(n) runtime for lsiding window
- O(1) space complexity for sliding window
---
Links :: [[#Example Code]] [[Computer Science]] [[Neetcode 150]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-10-08 11:07
