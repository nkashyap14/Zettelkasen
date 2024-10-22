# Car Fleet

#### Problem statement

There are `n` cars traveling to the same destination on a one-lane highway.

You are given two arrays of integers `position` and `speed`, both of length `n`.

- `position[i]` is the position of the `ith car` (in miles)
- `speed[i]` is the speed of the `ith` car (in miles per hour)

The **destination** is at position `target` miles.

A car can **not** pass another car ahead of it. It can only catch up to another car and then drive at the same speed as the car ahead of it.

A **car fleet** is a non-empty set of cars driving at the same position and same speed. A single car is also considered a car fleet.

If a car catches up to a car fleet the moment the fleet reaches the destination, then the car is considered to be part of the fleet.

Return the number of **different car fleets** that will arrive at the destination.
##### Example 1
```
Input: target = 10, position = [1,4], speed = [3,2]

Output: 1
```
##### Example 2
```
Input: target = 10, position = [4,1,0,7], speed = [2,2,1,1]

Output: 3
```
#### Solution
```
class Solution:
    def carFleet(self, target: int, position: List[int], speed: List[int]) -> int:
        stack = []
        
        pair = [(p, s) for p, s in zip(position, speed)]
        pair.sort(reverse=True)
        
        for p, s in pair:
            stack.append((target - p) / s)
            if len(stack) >= 2 and stack[-1] <= stack[-2]:
                stack.pop()

        return len(stack)
```

###### Programming Language Utilized:

- [[Python]]
###### Data structure utilized:
- [[Stack]]
#### Important Subdetails

#### Runtime of Optimal Solution
---
Links :: [[#Example Code]] [[Computer Science]] [[Neetcode 150]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-10-11 12:24
