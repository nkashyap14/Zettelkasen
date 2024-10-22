# Single Number

#### Problem statement

You are given a **non-empty** array of integers `nums`. Every integer appears twice except for one.

Return the integer that appears only once.

You must implement a solution with O(n)O(n) runtime complexity and use only O(1)O(1) extra space.
##### Example 1
```
Input: nums = [3,2,3]

Output: 2
```
##### Example 2
```
Input: nums = [7,6,6,7,8]

Output: 8
```
#### Solution
```
class Solution:
    def singleNumber(self, nums: List[int]) -> int:
        res = 0
        for n in nums:
	        #perform xor operation on every number in the list
            res = res ^ n

        return res
```

###### Programming Language Utilized:

- [[Python]]
###### Data structure utilized:

- [[XOR]]
- [[Bit Manipulation]]
#### Important Subdetails

- Because xor sets the bits that are equal to each other as 0 since we know all the values are duplciates except one xoring all the values of the array together will actually just give us the value of the single input.
#### Runtime of Optimal Solution
---
Links :: [[#Example Code]] [[Computer Science]] [[Neetcode 150]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-10-10 14:07
