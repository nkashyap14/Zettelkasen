# Combination Target Sum II

#### Problem statement
You are given an array of integers `candidates`, which may contain duplicates, and a target integer `target`. Your task is to return a list of all **unique combinations** of `candidates` where the chosen numbers sum to `target`.

Each element from `candidates` may be chosen **at most once** within a combination. The solution set must not contain duplicate combinations.

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
    def combinationSum2(self, candidates: List[int], target: int) -> List[List[int]]:
        candidates.sort()
        res= []
        def combinationSum(i, cur, total):
            if total == target:
                res.append(cur[:])
                return

            if total > target or i >= len(candidates):
                return

            cur.append(candidates[i])
            combinationSum(i + 1, cur, total + candidates[i])

            cur.pop()

            while i + 1 < len(candidates) and candidates[i] == candidates[i + 1]:
                i += 1

            combinationSum(i + 1, cur, total)            
        combinationSum(0, [], 0)

        return res
```

#### Solution 2:
```
class Solution:
    def combinationSum2(self, candidates: List[int], target: int) -> List[List[int]]:
        candidates.sort()
        res= []

        def combinationSum(i, candidates, target, curr_group):
            curr_group_sum = sum(curr_group)
            if curr_group_sum == target:
                res.append(curr_group[:])
                return
  
            if curr_group_sum > target or i >= len(candidates):
                return
            curr_group.append(candidates[i])
            combinationSum(i + 1, candidates, target, curr_group)
            
            curr_group.pop()
            temp = i
            while temp + 1 < len(candidates) and candidates[temp + 1] == candidates[temp]:
                temp += 1
            combinationSum(temp + 1, candidates, target, curr_group)

        combinationSum(0, candidates, target, [])
        return res
```

###### Programming Language Utilized:
 - [[Python]]
###### Data structure utilized:
- [[Backtracking]]

###### Prerequisites:

- [[Subsets II]]
- [[Combination Target Sum]]
#### Important Subdetails

- Reason solution 2 is more inefficient is we don't have to pass in candidates and target into our nested function
- Also don't need to calculate sum every function call. Keep a running total int and pass it through
- The idea here is that each number can either be included in the calculation or not. But the niche thing to understand here is that in the case we choose not to include the number then we should also skip all other instances of that number in the array
	- which is what the while loop does

#### Runtime of Optimal Solution

- Time complexity: O(n * 2^n): reason is each of the n elements we have a decision include or not so 2^n for combinations. and then every time we create a copy of the result so worst case is n * 2^n 
- Space complexity: O(n)
---
Links :: [[#Example Code]] [[Computer Science]] [[Neetcode 150]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-11-13 09:48
