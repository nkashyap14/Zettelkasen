# Two Integer Sum II

#### Problem statement
Given an array of integers `numbers` that is sorted in **non-decreasing order**.

Return the indices (**1-indexed**) of two numbers, `[index1, index2]`, such that they add up to a given target number `target` and `index1 < index2`. Note that `index1` and `index2` cannot be equal, therefore you may not use the same element twice.

There will always be **exactly one valid solution**.

Your solution must use O(1)O(1) additional space.

##### Example 1
```
Input: numbers = [1,2,3,4], target = 3

Output: [1,2]
```
#### Solution
```
class Solution:
    def twoSum(self, numbers: List[int], target: int) -> List[int]:
        l, r = 0, len(numbers) - 1
        while l < r:
            calc = numbers[l] + numbers[r]
            if calc == target:
                return [l + 1, r + 1]
            elif calc < target:
                l += 1
            else:
                r -= 1
```

###### Programming Language Utilized:

- [[Python]]
###### Data structure utilized:

- [[Two Pointers]]
#### Important Subdetails
- If the calculated target is higher than that means we need to reduce the target so we decrement the r while if its lower we increment l. Reason is we know this array is a non-decreasing order
- Had to use two pointers as this is O(1) space requirement otherwise hashmap possibility existed

#### Runtime of Optimal Solution

- O(n) as there is only one loop. Worst case is when the last two nums are the values tto return
---
Links :: [[#Example Code]] [[Computer Science]] [[Neetcode 150]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-10-03 13:55
