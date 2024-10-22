# Maximum Subarray

#### Problem statement

Given an array of integers `nums`, find the subarray with the largest sum and return the sum.

A **subarray** is a contiguous non-empty sequence of elements within an array.
##### Example 1
```
Input: nums = [2,-3,4,-2,2,1,-1,4]

Output: 8
```
##### Example 2
```
Input: nums = [-1]

Output: -1
```
#### Solution
```
class Solution:
    def maxSubArray(self, nums: List[int]) -> int:
        l, r = 0, 0
       
        res = float('-inf')
        total = 0
        while r < len(nums):
            total += nums[r]
            res = max(res, total)
            if total < 0:
                l = r + 1
                total = 0
            r += 1
        return res
```

#### Solution 2
```
class Solution:
    def maxSubArray(self, nums: List[int]) -> int:
        res = nums[0]

        total = 0
        for n in nums:
            total += n
            res = max(res, total)
            if total < 0:
                total = 0
        return res
```
###### Programming Language Utilized:

- [[Python]]
###### Data structure utilized:

- [[Sliding Window]]
#### Important Subdetails

- Essentially this is a sliding window problem. We keep a running total of the subarray sum. The question becomes as is usual with sliding window problems when to invalidate the window. The condition this time is when the running total of the window becomes < 0 because that means there is no value to keeping that subarray. So that is when we shift the left pointer to the right + 1. 
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
Date :: 2024-10-22 11:15
