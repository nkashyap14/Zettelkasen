# Min-Cost-Climbing-Stairs

#### Problem statement

You are given an array of integers `cost` where `cost[i]` is the cost of taking a step from the `ith` floor of a staircase. After paying the cost, you can step to either the `(i + 1)th` floor or the `(i + 2)th` floor.

You may choose to start at the index `0` or the index `1` floor.

Return the minimum cost to reach the top of the staircase, i.e. just past the last index in `cost`.
##### Example 1
```
Input: cost = [1,2,3]

Output: 2
```
##### Example 2
```
Input: cost = [1,2,1,2,1,1,1]

Output: 4

```
#### Solution 1: Brute force
```
class Solution:
    def minCostClimbingStairs(self, cost: List[int]) -> int:
        def minCost(currCost, i):
            if i > len(cost):
                return float('inf')

            if i == len(cost):
                return currCost

            currCost += cost[i]
            return min(minCost(currCost, i + 1), minCost(currCost, i + 2))

        res = min(minCost(0, 0), minCost(0, 1))

        return res
```

#### Solution 2: Bottom Up
```
class Solution:
    def minCostClimbingStairs(self, cost: List[int]) -> int:
        for i in range(len(cost) - 3, -1, -1):
            cost[i] += min(cost[i + 1], cost[i + 2])
  
        return min(cost[0], cost[1])
```

###### Programming Language Utilized:

- [[Python]]
###### Data structure utilized:

- [[Dynamic Programming]]
#### Important Subdetails

- The brute force operation is O(2^n). Very inefficient. Essentially a decision tree branching. Each decision has two optiosn and the tree has depth n with n being the number of items in the array
- The bottom up solution hinges on the fact that from the end of the array the last 2 items the most efficient way to get to the end is by picking itself. Then from there we build the min cost of the other problems by just choosing the min out of the two choices available for it. From there we build the sub problems from bottom up and it ends up being a linear run time of O(n)

#### Runtime of Optimal Solution

- O(n) runtime, O(1) space complexity
---
Links :: [[#Example Code]] [[Computer Science]] [[Neetcode 150]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-10-14 16:07
