# Course-Schedule

#### Problem statement

You are given an array `prerequisites` where `prerequisites[i] = [a, b]` indicates that you **must** take course `b` first if you want to take course `a`.

The pair `[0, 1]`, indicates that must take course `1` before taking course `0`.

There are a total of `numCourses` courses you are required to take, labeled from `0` to `numCourses - 1`.

Return `true` if it is possible to finish all courses, otherwise return `false`.

##### Example 1
```
Input: numCourses = 2, prerequisites = [[0,1]]

Output: true
```
##### Example 2
```
Input: numCourses = 2, prerequisites = [[0,1],[1,0]]

Output: false
```
#### Solution
```
from collections import defaultdict
class Solution:
    def canFinish(self, numCourses: int, prerequisites: List[List[int]]) -> bool:
        graph = defaultdict(list)

        for a, b in prerequisites:
            graph[a].append(b)  

        def cycle(course, seen):
            if course in seen:
                return False
            if graph[course] == []:
                return True
            seen.add(course)
            for prereq in graph[course]:
                if not cycle(prereq, seen):
                    return False
            graph[course] = []
            return True

        for c in range(numCourses):
            if not cycle(c, set()):
                return False

        return True
```

#### Solution 2:
```
class Solution:
    def canFinish(self, numCourses: int, prerequisites: List[List[int]]) -> bool:
        # Map each course to its prerequisites
        preMap = {i: [] for i in range(numCourses)}
        for crs, pre in prerequisites:
            preMap[crs].append(pre)

        # Store all courses along the current DFS path
        visiting = set()

        def dfs(crs):
            if crs in visiting:
                # Cycle detected
                return False
            if preMap[crs] == []:
                return True

            visiting.add(crs)
            for pre in preMap[crs]:
                if not dfs(pre):
                    return False
            visiting.remove(crs)
            preMap[crs] = []
            return True

        for c in range(numCourses):
            if not dfs(c):
                return False
        return True

```
###### Programming Language Utilized:

- [[Python]]
###### Data structure utilized:

- [[Graph]]
- [[depth first search]]
#### Important Subdetails

- Have to first create an adjacency list
	- Can use default dict
	- also can use list comprehension like this adj = {i : [] for i in range(numCourses)}
- Then we just detect if there is a cycle
	- In the dfs for the cycle if the adjacency_list is emtpy just return true
- To remove redundant work aka not having to check courses that we know the cycle is good for at the end of the dfs before returning true just set the adjacency list for that course to zero
- Option 3 is topological sort

#### Runtime of Optimal Solution

- Time complexity is O(V + E) where V is vertexes and E is edges
- Space complexity is O(V + E) where V is number of courses and E is number of prereqs. Because we build the set
---
Links :: [[#Example Code]] [[Computer Science]] [[Neetcode 150]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-10-22 11:29
