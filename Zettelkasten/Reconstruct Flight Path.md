# Reconstruct Flight Path

#### Problem statement

You are given a list of flight tickets `tickets` where `tickets[i] = [from_i, to_i]` represent the source airport and the destination airport.

Each `from_i` and `to_i` consists of three uppercase English letters.

Reconstruct the itinerary in order and return it.

All of the tickets belong to someone who originally departed from `"JFK"`. Your objective is to reconstruct the flight path that this person took, assuming each ticket was used exactly once.

If there are multiple valid flight paths, return the lexicographically smallest one.

- For example, the itinerary `["JFK", "SEA"]` has a smaller lexical order than `["JFK", "SFO"]`.

You may assume all the tickets form at least one valid flight path.
##### Example 1
```
Input: tickets = [["BUF","HOU"],["HOU","SEA"],["JFK","BUF"]]

Output: ["JFK","BUF","HOU","SEA"]
```
##### Example 2
```
Input: tickets = [["HOU","JFK"],["SEA","JFK"],["JFK","SEA"],["JFK","HOU"]]

Output: ["JFK","HOU","JFK","SEA","JFK"]
```
#### Solution: Depth First Search
```
class Solution:
    def findItinerary(self, tickets: List[List[str]]) -> List[str]:
        tickets.sort()
        
        adj = {src: [] for src, dst in tickets}

        for src, dst in tickets:
            adj[src].append(dst)
        res = ["JFK"]

        def dfs(src):
            if len(res) == len(tickets) + 1:
                return True
            
            #no outgoing edges
            if src not in adj:
                return False

            temp = list(adj[src])
            for i, v in enumerate(temp):
                adj[src].pop(i)
                res.append(v)

                if dfs(v):
                    return True

                adj[src].insert(i, v)
                res.pop()
            return False

        dfs("JFK")


        return res
```


#### Solution 2: Recursive
```
class Solution:
    def findItinerary(self, tickets: List[List[str]]) -> List[str]:

        adj = defaultdict(list)

        for src, dst in sorted(tickets)[::-1]:
            adj[src].append(dst)

        res = []

        def dfs(src):
            while adj[src]:
                dst = adj[src].pop()
                dfs(dst)

            res.append(src)

        dfs('JFK')

        return res[::-1]
```


#### Solution 3: Iterative
```
class Solution:
    def findItinerary(self, tickets: List[List[str]]) -> List[str]:

        adj = defaultdict(list)

        for src, dst in sorted(tickets)[::-1]:
            adj[src].append(dst)

        stack = ["JFK"]
        res = []

        while stack:
            curr = stack[-1]
            if not adj[curr]:
                res.append(stack.pop())
            else:
                stack.append(adj[curr].pop())

        return res[::-1]
```
###### Programming Language Utilized:

- [[Python]]
###### Data structure utilized:

- First solution uses [[depth first search]] and [[Backtracking]]
- Second + 3rd solution are different implementations of [[Hierholzer's Algorithm]]
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
Date :: 2025-02-04 10:54
