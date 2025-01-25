# Kth Largest Element in an Array

#### Problem statement

Given an unsorted array of integers `nums` and an integer `k`, return the `kth` largest element in the array.

By `kth` largest element, we mean the `kth` largest element in the sorted order, not the `kth` distinct element.

Follow-up: Can you solve it without sorting?
##### Example 1
```
Input: nums = [2,3,1,5,4], k = 2

Output: 4
```
##### Example 2
```
Input: nums = [2,3,1,1,5,5,4], k = 3

Output: 4
```
#### Solution 1
```
class Solution:
    def findKthLargest(self, nums: List[int], k: int) -> int:
        nums = [num * -1 for num in nums]
        heapq.heapify(nums)
  
        while k > 1:
            heapq.heappop(nums)
            k -= 1

        return heapq.heappop(nums) * -1
```


#### Solution 2:
```
# Quick Select
# Time complexity: O(n) in average, O(n^2) in worst case
class Solution:
    def findKthLargest(self, nums: List[int], k: int) -> int:
        k = len(nums) - k
        left, right = 0, len(nums) - 1

        while left < right:
            pivot = self.partition(nums, left, right)

            if pivot < k:
                left = pivot + 1
            elif pivot > k:
                right = pivot - 1
            else:
                break

        return nums[k]

    def partition(self, nums: List[int], left: int, right: int) -> int:
        pivot, fill = nums[right], left

        for i in range(left, right):
            if nums[i] <= pivot:
                nums[fill], nums[i] = nums[i], nums[fill]
                fill += 1

        nums[fill], nums[right] = nums[right], nums[fill]

        return fill
```
###### Programming Language Utilized:

- [[Python]]
###### Data structure utilized:

- [[Heap]] solution 1
- [[Two Pointers]] solution 2
#### Important Subdetails

- Solution one just involves a max heap. negate the keys put it into an array and then pop till k = 1. The final pop is the value that you are looking for
- Solution two involves a variation of the [[Quicksort]] algorithm. Variation because this time when we pick a pivot and partition the array because we know that len(nums) - k  gives us the index in a sorted array that we would want we could just continue using the quicksort algorithm and search in the left or right array depending on which side the answer is going to be in

#### Runtime of Optimal Solution

- Solution one run time is O(n) to build the heap and then klog(n) which dominates to pop from the heap
	- Each heap pop is log(n)
- Solution 2 average run time is O(n) but if the partition is chosen suboptimally in the worst case can end up being O(n^2) as we are essentially dropping just one element from the array each time
	- Average run time is big O(n) as we only look at one half of the array each time
		- So its O(n) first time + O(n/2) + O(n/4) + ... infinite series which ends up evaluation to O(2n) where the 2 gets removed because the n dominates
---
Links :: [[#Example Code]] [[Computer Science]] [[Neetcode 150]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-10-13 16:47
