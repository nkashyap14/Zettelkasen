# House Robber II

#### Problem statement

You are given an integer array `nums` where `nums[i]` represents the amount of money the `i`th house has. The houses are arranged in a circle, i.e. the first house and the last house are neighbors.

You are planning to rob money from the houses, but you cannot rob **two adjacent houses** because the security system will automatically alert the police if two adjacent houses were _both_ broken into.

Return the _maximum_ amount of money you can rob **without** alerting the police.
##### Example 1
```
Input: nums = [3,4,3]

Output: 4
```
##### Example 2
```
Input: nums = [2,9,8,3,6]

Output: 15
```
#### Solution
```
class Solution:
    def rob(self, nums: List[int]) -> int:
        return max(nums[0], self.helper(nums[:-1]), self.helper(nums[1:]))
        
    def helper(self,nums):
        rob1, rob2 = 0, 0
        for n in nums:
            newRob = max(rob1 + n, rob2)
            rob1 = rob2
            rob2 = newRob
        return rob2
```

###### Programming Language Utilized:

###### Data structure utilized:
#### Important Subdetails

- Similar to [[House Robber]] we apply same solution except because of hte circular we have to run the logic twice. once on the first subarray excluding last value and one on subarray excluding first value. to handle edge case of only one value in the array include a max calculation of nums[0]
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
Date :: 2024-12-03 17:03
