# House Robber

#### Problem statement

You are given an integer array `nums` where `nums[i]` represents the amount of money the `i`th house has. The houses are arranged in a straight line, i.e. the `i`th house is the neighbor of the `(i-1)`th and `(i+1)`th house.

You are planning to rob money from the houses, but you cannot rob **two adjacent houses** because the security system will automatically alert the police if two adjacent houses were _both_ broken into.

Return the _maximum_ amount of money you can rob **without** alerting the police.
##### Example 1
```
Input: nums = [1,1,3,3]

Output: 4
```
##### Example 2
```
Input: nums = [2,9,8,3,6]

Output: 16
```
#### Solution
```
class Solution:
    def rob(self, nums: List[int]) -> int:
        rob1, rob2 = 0, 0
        for n in nums:
            temp = max(n + rob1, rob2)
            rob1 = rob2
            rob2 = temp
        return rob2
```

###### Programming Language Utilized:

- [[Python]]
###### Data structure utilized:

- [[Dynamic Programming]]
#### Important Subdetails

- The intuition of this problem bases on the idea that the recurrence relation is that max rob is equal to max(array[0] + rob[2: n], rob[1:n]) or basically that either we take the first value and add it with the maximum robbing value of thee 3rd element onto the end of the array or we skip the first value and get the maximum robbing value from the second element on and we take the max of those two options
- This allows us to calculate it with 2 variables which hold the max robbing position from the 2 indices before. THis allows us to get the max rob value at whatever index we are iterating from.
	- it is either going to be index value + rob1 (two indexes back max) or the rob2 (one index back max rob) whichever is greater
	- then we move rob1 forward one spot so we set it = rob2
	- and we move rob2 one step forward so we set it ot he temp value we calculated
	- by the end of the iteration rob2 will be at the end of the array and will represent hte maximum robbing we can do through the array
#### Runtime of Optimal Solution

- O(n) runtime
- O(1) space complexity
---
Links :: [[#Example Code]] [[Computer Science]] [[Neetcode 150]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-12-03 16:30
