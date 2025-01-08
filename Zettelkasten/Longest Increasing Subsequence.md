# Longest Increasing Subsequence

#### Problem statement

Given an integer array `nums`, return the _length_ of the longest strictly _increasing_ subsequence.

A **subsequence** is a sequence that can be derived from the given sequence by deleting some or no elements without changing the relative order of the remaining characters.

- For example, `"cat"` is a subsequence of `"crabt"`.
##### Example 1
```
Input: nums = [9,1,4,2,3,3,7]

Output: 4
```
##### Example 2
```
Input: nums = [0,3,1,3,2,3]

Output: 4
```
#### Solution
```
class Solution:
    def lengthOfLIS(self, nums: List[int]) -> int:
        seen = {}
        def dfs(i, j):
            if i == len(nums):
                return 0

            if (i, j) in seen:
                return seen[(i, j)]

            LIS = dfs(i + 1, j) #if we don't incolude the index
  
            #if we are at the beginning of the array include it by default
            if j == -1 or nums[j] < nums[i]:
                #if not at beginning of array only incldue this number if its > previous num
                LIS = max(LIS, 1 + dfs(i + 1, i))

            seen[(i, j)] = LIS
            return LIS

        return dfs(0, -1)
```


#### Solution 2: 
```
class Solution:
    def lengthOfLIS(self, nums: List[int]) -> int:
        LIS = [1] * len(nums)
        for i in range(len(nums) - 1, -1, -1):
            for j in range(i + 1, len(nums)):
                if nums[i] < nums[j]:
                    LIS[i] = max(LIS[i], LIS[j] + 1)

        return max(LIS)
```
###### Programming Language Utilized:

- [[Python]]
###### Data structure utilized:

- [[Dynamic Programming]]
#### Important Subdetails

#### Runtime of Optimal Solution

- O(n^2) time + O(n) space for bottom up 
---
Links :: [[#Example Code]] [[Computer Science]] [[Neetcode 150]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2025-01-02 14:05
