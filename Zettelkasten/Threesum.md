# Threesum

#### Problem statement

Given an integer array `nums`, return all the triplets `[nums[i], nums[j], nums[k]]` where `nums[i] + nums[j] + nums[k] == 0`, and the indices `i`, `j` and `k` are all distinct.

The output should _not_ contain any duplicate triplets. You may return the output and the triplets in **any order**.
##### Example 1
```
Input: nums = [-1,0,1,2,-1,-4]

Output: [[-1,-1,2],[-1,0,1]]
```
##### Example 2
```
Input: nums = [0,1,1]

Output: []
```
#### Solution
```
class Solution:
    def threeSum(self, nums: List[int]) -> List[List[int]]:
        res = []
        nums.sort()
        for i, num in enumerate(nums):
            if num > 0:
                break
            if num == nums[i - 1]:
                continue
            l, r = i + 1, len(nums) - 1
            while l < r:
                calc = nums[l] + nums[r] + nums[i]
                if calc == 0:
                    res.append([nums[i], nums[l], nums[r]])
                    l += 1
                    r -= 1
                    #incrementing in the case that num[l] is a duplicate we don't want duplicate entries. dont have to do so for r as we account for i and l
                    while nums[l] == nums[l - 1] and l < r:
                        l += 1
                elif calc > 0:
                    r -= 1
                else:
                    l += 1
        return res
```

###### Programming Language Utilized:

- [[Python]]
###### Data structure utilized:

- [[Two Pointers]]
#### Important Subdetails

- This solution builds on the [[Two Integer Sum II]] problem. The same two pointer mechanism is used. The initial process is selected a non duplicate i to then use. Then we do the two sum calculation on the l, r and simply include the value located at i in the calculation
#### Runtime of Optimal Solution

- O(n log n) for the python sort and then + O(n^2) for the two nested loops, the while and the for loop. The O(n^2) overrides and results in a O(n^2) run time
---
Links :: [[#Example Code]] [[Computer Science]] [[Neetcode 150]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-10-03 14:16
