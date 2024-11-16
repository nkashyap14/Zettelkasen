# Combination Target Sum

#### Problem statement
You are given an array of **distinct** integers `nums` and a target integer `target`. Your task is to return a list of all **unique combinations** of `nums` where the chosen numbers sum to `target`.

The **same** number may be chosen from `nums` an **unlimited number of times**. Two combinations are the same if the frequency of each of the chosen numbers is the same, otherwise they are different.

You may return the combinations in **any order** and the order of the numbers in each combination can be in **any order**.

##### Example 1
```
```
##### Example 2
```
```
#### Solution
```
class Solution:
    def combinationSum(self, nums: List[int], target: int) -> List[List[int]]:
        res = []
        def dfs(i , subset , currTarget):
            if i >= len(nums) or currTarget > target:
                return
            if currTarget == target:
                res.append(subset.copy())
                return

            subset.append(nums[i])
            dfs(i, subset, currTarget + nums[i])
            subset.pop()
            dfs(i + 1, subset, currTarget)
        dfs(0, [], 0)
        return res
```

###### Programming Language Utilized:

- [[Python]]
###### Data structure utilized:

- [[Backtracking]]
#### Important Subdetails

- Each number has the option to either include it or not. We can include each number multiple times as well so when we pass the case we include it we pass it in at the same index so that the backtracking can branch to include it n times or 1 time etc.

#### Runtime of Optimal Solution
---
Links :: [[#Example Code]] [[Computer Science]] [[Neetcode 150]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-11-13 09:54
