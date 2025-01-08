# Gas Station

#### Problem statement

There are `n` gas stations along a circular route. You are given two integer arrays `gas` and `cost` where:

- `gas[i]` is the amount of gas at the `ith` station.
- `cost[i]` is the amount of gas needed to travel from the `ith` station to the `(i + 1)th` station. (The last station is connected to the first station)

You have a car that can store an unlimited amount of gas, but you begin the journey with an empty tank at one of the gas stations.

Return the starting gas station's index such that you can travel around the circuit once in the clockwise direction. If it's impossible, then return `-1`.

It's guaranteed that at most one solution exists.
##### Example 1
```
Input: gas = [1,2,3,4], cost = [2,2,4,1]

Output: 3
```
##### Example 2
```
Input: gas = [1,2,3], cost = [2,3,2]

Output: -1
```
#### Solution
```
class Solution:
    def canCompleteCircuit(self, gas: List[int], cost: List[int]) -> int:
        #no way we will ever be able to complete a circuit as the cost is greater than gas available

        if sum(gas) < sum(cost):
            return -1

        total = 0
        res = 0

        for i in range(len(gas)):
            total += (gas[i] - cost[i])

            if total < 0:
                total = 0
                res = i + 1
        return res
```

###### Programming Language Utilized:

- [[Python]]
###### Data structure utilized:

- [[Greedy]]
#### Important Subdetails

#### Runtime of Optimal Solution

- O(n) runtime
---
Links :: [[#Example Code]] [[Computer Science]] [[Neetcode 150]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2025-01-05 20:51
