# Maximum Product Subarray

#### Problem statement

Given an integer array `nums`, find a **subarray** that has the largest product within the array and return it.

A **subarray** is a contiguous non-empty sequence of elements within an array.

You can assume the output will fit into a **32-bit** integer.
##### Example 1
```
Input: nums = [1,2,-3,4]

Output: 4
```
##### Example 2
```
Input: nums = [-2,-1]

Output: 2
```
#### Solution
```
class Solution:
    def maxProduct(self, nums: List[int]) -> int:
        res = nums[0]
        curMin, curMax = 1, 1

        for num in nums:
            tmp = curMax * num
            curMax = max(curMax * num, curMin * num, num)
            curMin = min(tmp, curMin * num, num)
            res = max(curMax, res)

        return res
```

###### Programming Language Utilized:

- [[Python]]
###### Data structure utilized:

- [[Dynamic Programming]]
#### Important Subdetails

- [[Kadane's Algorithm]]
- Need to track the minimum as well because negative numbers can cause the max value to flip. The negative times the previous min makes it into the current max while the negative times the previous max makes it the current min
- Check for yourself for the edge case where both the current min and max are  a negative number
	- Ex: [-1, 8]

#### Runtime of Optimal Solution
- O(n) runtime, O(1) space complexity
---
Links :: [[#Example Code]] [[Computer Science]] [[Neetcode 150]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2025-01-02 12:32
