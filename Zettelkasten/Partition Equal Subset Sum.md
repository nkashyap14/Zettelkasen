# Partition Equal Subset Sum

#### Problem statement

Given a non-empty array of positive integers, determine if the array can be divided into two subsets so that the sum of both subsets is equal.

**Constraints:**

- 1≤1≤ `nums.length` ≤200≤200
- 1≤1≤ `nums[i]` ≤100≤100

##### Example 1
```
```
##### Example 2
```
```
#### Solution
```
def can_partition_array(nums):
    total = sum(nums)
    # Replace this placeholder return statement with your code
    if total % 2 == 1:
      return False
    
    subset_sum = total // 2
    
    dp = [[False] * (len(nums) + 1) for _ in range(subset_sum + 1)]
    
    for i in range(0, len(nums) + 1):
      #for a sum of 0 we can make it for all possible elements available for us because we just include no elements
      dp[0][i] = True
    
    for i in range(1, subset_sum + 1):
      for j in range(1, len(nums) + 1):
        if nums[j - 1] > i:
          dp[i][j] = dp[i][j - 1]
        else:
          dp[i][j] = dp[i - nums[j - 1]][j - 1] or dp[i][j - 1]
          
    return dp[subset_sum][len(nums)]
```

###### Programming Language Utilized:

- [[Python]]
###### Data structure utilized:
#### Important Subdetails

- Know there is a sum we need to reach such that it can be split in half with 2 arrays representing it.
- If sum is odd know answer is false
- From there take the half of the sum. that is the value we seek to reach too
- The constraints of our dp table are the sum that we are adding to, and the elements that we ahve available
- For each element we have two decisions, if it is > than the sum than we auto don't include it so we just set that dp value to whatever the previous elements value was at the same sum level
- However in the case where it can be included we have 2 options, either include it or don't
- If we don't include it than we know we are looking in the dp table for the same sum value but to see if we can reach that sum with the j -1 elements aka without incliuding it or if we can reach that sum's vbalue minus the current number value using the last j - 1 elements. 
- So the truth value at i, j represnets whether we can create sum i with the j total elements 
#### Runtime of Optimal Solution
- O(n * s) runtime where n is size of input array and s is sum of the array Same space complexity. due to the lookup table
---
Links :: [[#Example Code]] [[Computer Science]] [[Educative]] [[Dynamic Programming]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2025-01-02 14:39
