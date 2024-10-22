# Last Stone Weight

#### Problem statement

You are given an array of integers `stones` where `stones[i]` represents the weight of the `ith` stone.

We want to run a simulation on the stones as follows:

- At each step we choose the **two heaviest stones**, with weight `x` and `y` and smash them togethers
- If `x == y`, both stones are destroyed
- If `x < y`, the stone of weight `x` is destroyed, and the stone of weight `y` has new weight `y - x`.

Continue the simulation until there is no more than one stone remaining.

Return the weight of the last remaining stone or return `0` if none remain.
##### Example 1
```
Input: stones = [2,3,6,2,4]

Output: 1
```
##### Example 2
```
Input: stones = [1,2]

Output: 1
```
#### Solution
```
class Solution:
    def lastStoneWeight(self, stones: List[int]) -> int:
        stones = [num * -1 for num in stones]
        heapq.heapify(stones)

        while stones and len(stones) > 1:
            x, y = heapq.heappop(stones), heapq.heappop(stones)
            if y > x:
                x = x - y
                heapq.heappush(stones, x)

        return stones[0] * -1 if stones else 0
```

###### Programming Language Utilized:

- [[Python]]
###### Data structure utilized:

- [[Heap]]
#### Important Subdetails

- Python has no max heap so the way we use a max heap is by negating the values of the original stones array

#### Runtime of Optimal Solution

- N(log n), O(n) to build the array. However O(N log n) dominates. The reason nlogn arises is there are log n to push and pop from a heap and we will be doing that up to n times
---
Links :: [[#Example Code]] [[Computer Science]] [[Neetcode 150]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-10-13 07:46
