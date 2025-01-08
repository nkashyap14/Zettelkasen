# Subsets II

#### Problem statement

You are given an array `nums` of integers, which may contain duplicates. Return all possible subsets.

The solution must **not** contain duplicate subsets. You may return the solution in **any order**.
##### Example 1
```
Input: nums = [1,2,1]

Output: [[],[1],[1,2],[1,1],[1,2,1],[2]]
```
##### Example 2
```
Input: nums = [7,7]

Output: [[],[7], [7,7]]
```
#### Solution
```
class Solution:
    def subsetsWithDup(self, nums: List[int]) -> List[List[int]]:
        res = []
        nums.sort()

        def dfs(n, subset):
            if n >= len(nums):
	            //need to append a copy.can do subset[::]. reason is if we append subset than it is a reference and as we pop across the array the changes will be reflected in our res array too
                res.append(subset.copy())
                return
                
            subset.append(nums[n])
            //two decisions to make, one is to create a subset with the number at position n
            dfs(n + 1, subset)
            subset.pop()

			//this is the second decision, where we create a subset without the number at position n. however because we know this is a sorted array with duplicates then we have to checck and move our pointer over to the last instance of the number we are choosing to skip. that is why we keep incrememnting while n + 1 is in the bounds of hte array and the num at n + 1 is == num at n
            while n + 1 < len(nums) and nums[n] == nums[n + 1]:
                n += 1

			//now that we know we are at the final duplicate we choose to call dfs on the next element knowing that we have skipped it. if this is an array of all duplicates then this call is what sets up the empty arrya as a subset.
            dfs(n + 1, subset)

        dfs(0, [])

  

        return res
```

###### Programming Language Utilized:

- [[Python]]
###### Data structure utilized:

- [[Backtracking]]
- [[depth first search]]
#### Important Subdetails

#### Runtime of Optimal Solution

- O(n log n) for the sort but that gets overridden by the O(n * 2^n ). The 2^n arises from the fact that there are n elements and for each fo them we have two decisions, include in a subset or don't. Then we multiply by n as the subsets take n to build.
---
Links :: [[#Example Code]] [[Computer Science]] [[Neetcode 150]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-10-23 16:17
