# Is Anagram

#### Problem statement

Given two strings s and t, return true if the two strings are anagrams of each other, otherwise return false

An anagram is a string that contains the exact same characters as another string, but the order of the characters

##### Example 1
```
Input: s = "racecar", t = "carrace"

Output: true
```
##### Example 2
```
Input: s = "racecar", t = "carrace"

Output: true
```
#### Solution
```
class Solution:
	def isAnagram(self, s: str, t: str) -> bool:
		if len(s) != len(t):
			return False
		countS, countT = {}, {}

		for i in range(len(s)):
			countS[s[i]] = 1 + countS.get(s[i], 0)
			countT[t[i]] = 1 + countT.get(t[i], 0)

		return countT == countS
```

###### Programming Language Utilized:

- [[Python]]
###### Data structure Utilized:

- [[Python Dictionary]]
- [[hashmap]]
#### Important Subdetails

#### Runtime of Optimal Solution

- O(n) as we iterate over both strings and simply populate two dictionaries with the counts of each
	- Each call incrementing the dictionary involves one set and a fixed cost call to get function
- Space complexity is O(k) where k is the size of the character set
	- assuming alphabet then worst case 26, could be larger for asccii ie 128, unicode larger
---
Links :: [[#Example Code]] [[Computer Science]] [[Neetcode 150]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-10-02 15:14
