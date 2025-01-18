# Cheapest Flights Within K Stops

#### Problem statement

There are `n` airports, labeled from `0` to `n - 1`, which are connected by some flights. You are given an array `flights` where `flights[i] = [from_i, to_i, price_i]` represents a one-way flight from airport `from_i` to airport `to_i` with cost `price_i`. You may assume there are no duplicate flights and no flights from an airport to itself.

You are also given three integers `src`, `dst`, and `k` where:

- `src` is the starting airport
- `dst` is the destination airport
- `src != dst`
- `k` is the maximum number of stops you can make (not including `src` and `dst`)

Return **the cheapest price** from `src` to `dst` with at most `k` stops, or return `-1` if it is impossible.
##### Example 1
```
Input: n = 4, flights = [[0,1,200],[1,2,100],[1,3,300],[2,3,100]], src = 0, dst = 3, k = 1

Output: 500
```
##### Example 2
```
Input: n = 3, flights = [[1,0,100],[1,2,200],[0,2,100]], src = 1, dst = 2, k = 1

Output: 200
```
#### Solution
```
class Solution:
    def findCheapestPrice(self, n: int, flights: List[List[int]], src: int, dst: int, k: int) -> int:
        prices = [float("inf")] * n
        prices[src] = 0

        for i in range(k + 1):
            tmpPrices = prices.copy()
            for src, dest, price in flights:
                #this routes source node is unreachable with having used i amount of stops so far
                if prices[src] == float("inf"):
                    continue

                if prices[src] + price < tmpPrices[dest]:
                    tmpPrices[dest] = prices[src] + price

            prices = tmpPrices

        return -1 if prices[dst] == float("inf") else prices[dst]
```

###### Programming Language Utilized:

###### Data structure utilized:

- [[Bellman's Ford Algorithm]]
#### Important Subdetails

#### Runtime of Optimal Solution

- O(E * K) where E is edges and K is the input parameter K stops
- O(V) space complexity where n is number of cities or V
---
Links :: [[#Example Code]] [[Computer Science]] [[Neetcode 150]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2025-01-16 09:30
