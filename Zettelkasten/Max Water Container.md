# Max Water Container

#### Problem statement
You are given an integer array `heights` where `heights[i]` represents the height of the ith bar.

You may choose any two bars to form a container. Return the _maximum_ amount of water a container can store.

##### Example 1
```
Input: height = [1,7,2,5,4,7,3,6]
Output: 36
```
##### Example 2
```
Input: height = [2,2,2]
Output: 4
```
#### Solution
```
class Solution:
	def maxArea(self, heights: List[int]) -> int:
	l, r = 0, len(heights) - 1
	res = 0

	while l < r:
		calc = (r - l) * min(heights[l], heights[r])
		res = max(res, calc)
		if heights[l] < heights[r]:
			l += 1
		else:
			r -= 1

	return res
```

###### Programming Language Utilized:

- [[Python]]
###### Data structure utilized:

- [[Two Pointers]]
#### Important Subdetails

- Similar to two sum in the sense that we are moving the pointer that has the less optimal value
- The reason we start at hte opposite ends and collapse is this is a maximization problem and one of the calculated values to maximize is (r - l) aka width, and the other thing to maximize is the minimum height which is why we try to keep the larger bar and move the other pointer to see if we can find a larger bar so the old large becomes the min
#### Runtime of Optimal Solution

- O(n) as there is only one loop iterating over the array of size N
- space complexity O(1) as we are only adding on fixed cost pointers
---
Links :: [[#Example Code]] [[Computer Science]] [[Neetcode 150]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-10-04 15:57
