# Two Sum

#### Problem statement
Given an array of integers `nums` and an integer `target`, return the indices `i` and `j` such that `nums[i] + nums[j] == target` and `i != j`.

You may assume that _every_ input has exactly one pair of indices `i` and `j` that satisfy the condition.

Return the answer with the smaller index first.
##### Example 1
```
Input: 
nums = [3,4,5,6], target = 7

Output: [0,1]
```
##### Example 2
```
Input: nums = [4,5,6], target = 10

Output: [0,2]
```
#### Solution
```
class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        temp = {}
        for i, num in enumerate(nums):
	        #can slightly optimize this by doing diff = target - num and then reusing that variable in the loop as opposed to doing calculation over and over
            if target - num in temp:
                return [temp[target - num], i]
            else:
                temp[num] = i
```
###### Programming Language Utilized:
- [[Python]]
###### Data structure utilized:
- [[Python Dictionary]]
- [[hashmap]]
#### Important Subdetails

#### Runtime of Optimal Solution

- Time complexity O(n) as we have to iterate over array once at most
- Space complexity O(n) as we might add every value to the hashmap
---
Links :: [[#Example Code]] [[Computer Science]] [[Neetcode 150]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-10-02 15:28
