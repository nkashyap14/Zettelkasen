# Duplicate Integer

#### Problem statement

- Given an integer array nums, return true if any value appears more than once in the array, otherwise return false
##### Example 1
```
Input: nums = [1, 2, 3, 3]

Output: true
```
##### Example 2
```
Input: nums = [1, 2, 3, 4]

Output: false
```
#### Solution
```
class Solution:
	def hasDuplicate(self, nums: List[int]) -> bool:
		hashset = set()

		for n in nums:
			if n in hashset:
				return True
			hashset.add(n)
		return False
```

###### Programming Language Utilized:
- [[Python]]
#### Important Subdetails

- In this case set is utilized because a set only holds one instance of a unique object
	- Allows us to save space
	- If the object is already in set then we know its duplicate
#### Runtime of Optimal Solution

- O(n) as we simply have one iterative loop over all contents of the list
---
Links :: [[#Example Code]] [[Computer Science]] [[Neetcode 150]]
Reference :: [[Python Set]]
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-10-02 14:59
