# Anagram Groups

#### Problem statement
Given an array of strings `strs`, group all _anagrams_ together into sublists. You may return the output in **any order**.

An **anagram** is a string that contains the exact same characters as another string, but the order of the characters can be different.
##### Example 1
```
Input: strs = ["act","pots","tops","cat","stop","hat"]

Output: [["hat"],["act", "cat"],["stop", "pots", "tops"]]
```
##### Example 2
```
Input: strs = ["x"]

Output: [["x"]]
```
#### Solution
```
class Solution:
	def groupAnagrams(self, strs: List[str]) -> List[List[str]]:
		ans = defaultdict(list)

		for s in strs:
			#utilized as a key to map to strings. the unique count is what identifies strings as anagrams of each other
			count = [0] * 26 
			for c in s:
				count[ord(c) - ord('a')] += 1
			#convert the count to a tuple as lists are unhashable
			ans[tuple(count)].append(s)

		return ans.values()
```

###### Programming Language Utilized:
- [[Python]]
###### Data structure utilized:

- [[hashmap]]
- [[Python defaultdict]]
#### Important Subdetails

- [[Python ord function]]
- The idea of this is that you create a frequency tuple of the characters for each string and then from there use that as the keyvalue and append it to a hashmap where keys are mapped to lists. The list contains all all the strings that have the same frequency count which is how we tell they are anagrams of each other. From there just return the dict.values()
#### Runtime of Optimal Solution

- Time complexiyt is O(m * n)
	- the n arises from the fact that we iterate over the n list of strings
	- the m is the average length of each string. it arises as we have to iterate over every string
- Space is the same 
---
Links :: [[#Example Code]] [[Computer Science]] [[Neetcode 150]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-10-02 15:45
