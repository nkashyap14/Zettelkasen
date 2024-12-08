# Course Schedule II

#### Problem statement


##### Example 1
```
```
##### Example 2
```
```
#### Solution
```
class Solution:
    def findOrder(self, numCourses: int, prerequisites: List[List[int]]) -> List[int]:
        adj = defaultdict(list)
        for a, b in prerequisites:
            adj[a].append(b)

        res = []
        seen, cycle = set(), set()
        def dfs(course):
            if course in cycle:
                return False
            if course in seen:
                return True
                
            cycle.add(course)
            
            for prereq in adj[course]:
                if not dfs(prereq):
                    return False
                    
            cycle.remove(course)
            seen.add(course)
            res.append(course)
            
            return True

        for i in range(numCourses):
            if not dfs(i):
                return []

        return res
```

###### Programming Language Utilized:

- [[Python]]
###### Data structure utilized:

- [[Set]]
- [[Graph]]
#### Important Subdetails

- Keep two sets. One seen for all the nodes seen while one is cycle which is keeping all the nodes currently visited on the dfs for the purposes of cycle detection

#### Runtime of Optimal Solution

- O(V + E) for runtime or O(P + N) where P is prerequisites which are the edges and N is the number of courses or the vertices
- Same for space complexity
---
Links :: [[#Example Code]] [[Computer Science]] [[Neetcode 150]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-12-03 16:11
