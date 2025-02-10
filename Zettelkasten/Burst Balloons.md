# Burst Balloons

#### Problem statement

You are given an array of integers `nums` of size `n`. The `ith` element represents a balloon with an integer value of `nums[i]`. You must burst all of the balloons.

If you burst the `ith` balloon, you will receive `nums[i - 1] * nums[i] * nums[i + 1]` coins. If `i - 1` or `i + 1` goes out of bounds of the array, then assume the out of bounds value is 1.

Return the maximum number of coins you can receive by bursting all of the balloons.

##### Example 1
```
Input: nums = [4,2,3,7]

Output: 167

Explanation:
nums = [4,2,3,7] --> [4,3,7] --> [4,7] --> [7] --> []
coins =  4*2*3    +   4*3*7   +  1*4*7  + 1*7*1 = 143
```
#### Solution
```
class Solution:
    def maxCoins(self, nums: List[int]) -> int:
        nums = [1] + nums + [1]
        dp = {}

        def dfs(l, r):
            if l > r:
                return 0
            if (l, r) in dp:
                return dp[(l, r)]

            dp[(l, r)] = 0
            for i in range(l, r + 1):
                #the value is being considered if we pop i last
                #so we are basically considering if the subarrays to the left
                #and right have been popped already so multiply them by 
                #the values to the left of the leftmost value in the left subarray
                #and same with right
                coins = nums[l - 1] * nums[i] * nums[r + 1]
                coins += dfs(l, i - 1) + dfs(i + 1, r)
                dp[(l, r)] = max(dp[(l, r)], coins)
            return dp[(l, r)]

        return dfs(1, len(nums) - 2)
```

###### Programming Language Utilized:

- [[Python]]
###### Data structure utilized:

- [[2D Dynamic Programming]]
- [[Memoization]]
#### Important Subdetails

- The trick of this problem hinges on the idea that we are going to consider the subproblem as if we choose each index as the one to pop last. from there we create two different subproblems of what are the max coins considering the left subarray left over and right subarray left over
- append 1 to the end and beginning of the nums array to account for the idea that we multiply by 1 if its at the edge rather than complicating the if logic

#### Runtime of Optimal Solution

- O(n^3) runtime and O(n^2) space complexity. N^2 because we are making a 2d cache
- N^3 runtime because an array with length n can have n^2 subarrays. And we are calculating for every subarray the idea that if at each position we were popping that value last so we are making n calls over each subarray so n * n^2
---
Links :: [[#Example Code]] [[Computer Science]] [[Neetcode 150]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2025-02-10 14:16
