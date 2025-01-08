# Permutations  (Neetcode)

#### Problem statement

Given an array `nums` of **unique** integers, return all the possible permutations. You may return the answer in **any order**.
##### Example 1
```
Input: nums = [1,2,3]

Output: [[1,2,3],[1,3,2],[2,1,3],[2,3,1],[3,1,2],[3,2,1]]
```
##### Example 2
```
Input: nums = [7]

Output: [[7]]
```
#### Solution 1
```
class Solution:
    def permute(self, nums: List[int]) -> List[List[int]]:
        if len(nums) == 0:
            return [[]]

        perms = self.permute(nums[1:])
        res = []
        for p in perms:
            for i in range(len(p) + 1):
                p_copy = p.copy()
                p_copy.insert(i, nums[0])
                res.append(p_copy)
        return res
```

#### Solution 2
```
class Solution:
    def permute(self, nums: List[int]) -> List[List[int]]:
        perms = [[]]
        
        for n in nums:
            new_perms = []
            for p in perms:
                for i in range(len(p) + 1):
                    p_copy = p.copy()
                    p_copy.insert(i, n)
                    new_perms.append(p_copy)
            perms = new_perms

        return perms
```
###### Programming Language Utilized:

- [[Python]]
###### Data structure utilized:

- [[Backtracking]]
#### Important Subdetails

- Recursion way is we are building from the ground up at base level and then over each level of permutations returend we are building new permutations by adding a new element that gets inserted at every possible position in the permutation. While building the recursion we are excluding the first element in the list every time
- Iterative way we are building the permutations as well however the intution behind it is that we come up with a new set of permutations every time with each number. As we build throughout the nums list we have to iterate over every one of those permutations and insert that new number at every possible position in that permutation.

#### Runtime of Optimal Solution

- Recursive solution:
	- O(n! * n^2): n! as there are n! permutations and we are making an O(n) insert call n times
	- space comlpexlity(O(n! * n)) as n! permutations of each average length n
---
Links :: [[#Example Code]] [[Computer Science]] [[Neetcode 150]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-10-10 19:11
