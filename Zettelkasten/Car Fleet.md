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

```
class Solution(object):
    def carFleet(self, target, position, speed):
        # Instead of creating pairs, just store indices sorted by position
        indices = sorted(range(len(position)), key=lambda i: position[i], reverse=True)
        stack = []
        # Use indices to reference original arrays
        for i in indices:
            time = float(target - position[i]) / speed[i]
            stack.append(time)
            if len(stack) >= 2 and stack[-1] <= stack[-2]:
                stack.pop()

        return len(stack)
```
###### Programming Language Utilized:

- [[Python]]
###### Data structure utilized:
- [[Stack]]
#### Important Subdetails

- Solution 1: Sort by zipped pairs of position and speed
	- Then do the distance calculation which is target - pos and divide it by the speed to get total time taken
	- add the time to the stack only but pop it only if it is <= the time that the car that starts at a closer position to it takes. in that case pop it because it will be a fleet with that car otherwise leave it on the stack because it is a head of its own fleet now
	- return the lenght of the stack as the number of fleets
- Optimal solution just involves using a sorted array of indices of the position and then using that index to do the calculation instead of having to zip arrays together

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
