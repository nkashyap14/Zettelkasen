# Find Duplicate Integer

#### Problem statement
You are given an array of integers `nums` containing `n + 1` integers. Each integer in `nums` is in the range `[1, n]` inclusive.

Every integer appears **exactly once**, except for one integer which appears **two or more times**. Return the integer that appears more than once.

Follow-up: Can you solve the problem **without** modifying the array `nums` and using O(1) extra space?
##### Example 1
```
Input: nums = [1,2,3,2,2]

Output: 2
```
##### Example 2
```
Input: nums = [1,2,3,4,4]

Output: 4
```
#### Solution:
```
class Solution:
    def findDuplicate(self, nums: List[int]) -> int:
        slow, fast = 0, 0
        while True:
            slow, fast = nums[slow], nums[nums[fast]]
            if slow == fast:
                break
                
        slow2 = 0
        while True:
            slow, slow2 = nums[slow], nums[slow2]
            if slow == slow2:
                break

        return slow
```
###### Programming Language Utilized:

- [[Python]]
###### Data structure utilized:

- [[2 Pointers]]
- [[Linked List]]
- [[Cycle detection]]
#### Important Subdetails

- If not O(1) extra space then its simple use a [[Set]]
- If required to use O(1) space can sort the array and then do a simple check till the end of the array if i-1 == i however can't sort it as you are not allowed to modify the array
- This is a linked list cycle problem
- [[Floyd's Algorithm]]
	- Tells you the beginning of a cycle in a linked list
- p till distance to start of cycle
- c to traverse whole cycle
- x is node where slow and fast intersect
- 2 * (slow travel) = fast travel
$$
2 *(p + c - x) = 2c - x + p
$$
- simplifies to
$$
p = x
$$
- aka the distance from start node to start of cycle is the same distance from where fast and slow intersect to start of cycle
	- so tahts why we start a second slow pointer at the start of cycle and continue traversing. when the two inteersect we are at the start of the cycle and the index that point points too is the duplicate

#### Runtime of Optimal Solution

- O(n) runtime
- O(1) space complexity
---
Links :: [[#Example Code]] [[Computer Science]] [[Neetcode 150]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-11-10 13:11
