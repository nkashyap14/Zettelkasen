# Median of Two Sorted Arrays

#### Problem statement

You are given two integer arrays `nums1` and `nums2` of size `m` and `n` respectively, where each is sorted in ascending order. Return the [median](https://en.wikipedia.org/wiki/Median) value among all elements of the two arrays.

Your solution must run in O(log(m+n))O(log(m+n)) time.
##### Example 1
```
Input: nums1 = [1,2], nums2 = [3]

Output: 2.0
```
##### Example 2
```
Input: nums1 = [1,3], nums2 = [2,4]

Output: 2.5
```
#### Solution
```
class Solution:
    def findMedianSortedArrays(self, nums1: List[int], nums2: List[int]) -> float:
        A, B = nums1, nums2

        total = len(nums1) + len(nums2)

        half = total // 2

        if len(A) > len(B):
            A, B = B, A

        l, r = 0, len(A) - 1


        while True:
            mid = (l + r) // 2
            #remaining number of elements we need to take from array B 1 indexed
            remaining = half - (mid + 1)
  
            #max value from left partition of A
            Aleft = A[mid] if mid >= 0 else float("-infinity")

            #min value from right partition of A
            Aright = A[mid + 1] if (mid + 1) < len(A) else float("infinity")

            #max value from b left parittion
            Bleft = B[remaining - 1] if remaining > 0 else float('-infinity')

            #min value from b right partition
            Bright = B[remaining] if (remaining) < len(B) else float("infinity")



            if Aleft <= Bright and Bleft <= Aright:
                #odd length
                if total % 2:
                    return min(Aright, Bright)
                return (max(Aleft, Bleft) + min(Aright, Bright)) / 2

            elif Aleft > Bright:
                r = mid - 1
            else:
                l = mid + 1
```

###### Programming Language Utilized:

- [[Python]]
###### Data structure utilized:

- [[Binary Search]]
#### Important Subdetails

#### Runtime of Optimal Solution  

- O(1) space complexity
- O(log(m + n)) runtime where m and n are elements in the two arrays
---
Links :: [[#Example Code]] [[Computer Science]] [[Neetcode 150]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2025-01-25 18:31
