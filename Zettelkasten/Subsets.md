# Subsets

#### Problem statement

Given an array `nums` of **unique** integers, return all possible subsets of `nums`.

The solution set must **not** contain duplicate subsets. You may return the solution in **any order**.
##### Example 1
```
Input: nums = [1,2,3]

Output: [[],[1],[2],[1,2],[3],[1,3],[2,3],[1,2,3]]
```
##### Example 2
```
Input: nums = [7]

Output: [[],[7]]
```
#### Solution
```
class Solution:
    def subsets(self, nums: List[int]) -> List[List[int]]:
        res, subset = [], []
        def dfs(n):
            if n >= len(nums):
                res.append(subset.copy())
                return

            subset.append(nums[n])
            dfs(n + 1)
            subset.pop()
            dfs(n + 1)

        dfs(0)
        return res
```

###### Programming Language Utilized:

- [[Python]]
###### Data structure utilized:

- [[Backtracking]]
- [[depth first search]]
#### Important Subdetails

- Can iterate on the dfs just using the index
- Need to append a copy of the subset because otherwise modifying its value will reflect the value in the res changes

#### Runtime of Optimal Solution

- Runtime: O(2^n * n): 2^n subsets and each subset could be of length n
---
Links :: [[#Example Code]] [[Computer Science]] [[Neetcode 150]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-10-10 18:18
