# Target Sum

#### Problem statement

You are given an array of integers `nums` and an integer `target`.

For each number in the array, you can choose to either add or subtract it to a total sum.

- For example, if `nums = [1, 2]`, one possible sum would be `"+1-2=-1"`.

If `nums=[1,1]`, there are **two different ways** to sum the input numbers to get a sum of `0`: `"+1-1"` and `"-1+1"`.

Return the number of **different ways** that you can build the expression such that the total sum equals `target`.
##### Example 1
```
Input: nums = [2,2,2], target = 2

Output: 3
```
##### Example 2
```
```
#### Solution
```
class Solution:
    def findTargetSumWays(self, nums: List[int], target: int) -> int:
        memo = {}
        #this dfs call returns from index i the total number of ways to sum to tareget
        def dfs(i, total):
            if i > len(nums):
                return 0
                
            if i == len(nums):
                memo[(i, total)] = (target == total)
                return memo[(i, total)]
            #for each number we can either take its positive, or its negative value
            #so do both
            memo[(i, total)] = dfs(i + 1, total + nums[i])
            memo[(i, total)] += dfs(i + 1, total - nums[i])

            return memo[(i, total)]

  

        return dfs(0, 0)
```


#### Solution 2: Bottom up 
```
class Solution:
    def findTargetSumWays(self, nums: List[int], target: int) -> int:

        n = len(nums)
        dp = [defaultdict(int) for _ in range(n + 1)]
        dp[0][0] = 1

        for i in range(n):
            for total, count in dp[i].items():
                dp[i + 1][total + nums[i]] += count
                dp[i + 1][total - nums[i]] += count


        return dp[n][target]
```
###### Programming Language Utilized:

- [[Python]]
###### Data structure utilized:

- [[2D Dynamic Programming]]
#### Important Subdetails

#### Runtime of Optimal Solution

- Time Complexity: O(n * m) where n is the length of the array nums and m is the sum of all the elements
- Same with space complexity
- Same for bottom up solution as well 
---
Links :: [[#Example Code]] [[Computer Science]] [[Neetcode 150]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2025-01-09 15:20
