# Course Schedule IV

#### Problem statement
There are a total of `numCourses` courses you have to take, labeled from `0` to `numCourses - 1`. You are given an array `prerequisites` where `prerequisites[i] = [ai, bi]` indicates that you **must** take course `ai` first if you want to take course `bi`.

- For example, the pair `[0, 1]` indicates that you have to take course `0` before you can take course `1`.

Prerequisites can also be **indirect**. If course `a` is a prerequisite of course `b`, and course `b` is a prerequisite of course `c`, then course `a` is a prerequisite of course `c`.

You are also given an array `queries` where `queries[j] = [uj, vj]`. For the `jth` query, you should answer whether course `uj` is a prerequisite of course `vj` or not.

Return _a boolean array_ `answer`_, where_ `answer[j]` _is the answer to the_ `jth` _query._

##### Example 1
```
**Input:** numCourses = 2, prerequisites = [[1,0]], queries = [[0,1],[1,0]]
**Output:** [false,true]
**Explanation:** The pair [1, 0] indicates that you have to take course 1 before you can take course 0.
Course 0 is not a prerequisite of course 1, but the opposite is true.
```
##### Example 2
```
**Input:** numCourses = 2, prerequisites = [], queries = [[1,0],[0,1]]
**Output:** [false,false]
**Explanation:** There are no prerequisites, and each course is independent.
```
#### Solution
```
class Solution(object):
    def checkIfPrerequisite(self, numCourses, prerequisites, queries):
        """
        :type numCourses: int
        :type prerequisites: List[List[int]]
        :type queries: List[List[int]]
        :rtype: List[bool]
        """

        adjList = {i: [] for i in range(numCourses)}
        indegree = [0] * numCourses

        for edge in prerequisites:
            adjList[edge[0]].append(edge[1])
            indegree[edge[1]] += 1

        q = deque()
        for i in range(numCourses):
	        # a class with no prerequisites so we can start with this class
            if indegree[i] == 0:
                q.append(i)

		#better to use a default dict set in terms of space complexity
        prereqs = defaultdict(set)#{i : set() for i in range(numCourses)}

        while q:
            node = q.popleft()
  
            for adj in adjList[node]:
                prereqs[adj].add(node)
                for pre in prereqs[node]:
                    prereqs[adj].add(pre)

                indegree[adj] -= 1
                if indegree[adj] == 0:
                    q.append(adj)

        answer = []

        for q in queries:
            answer.append(q[0] in prereqs[q[1]])

        return answer
```


#### Solution 2: My solution Inefficient
```
class Solution(object):
    def checkIfPrerequisite(self, numCourses, prerequisites, queries):
        """
        :type numCourses: int
        :type prerequisites: List[List[int]]
        :type queries: List[List[int]]
        :rtype: List[bool]
        """

        adj = {i : [] for i in range(numCourses)}
        revAdj = {i : [] for i in range(numCourses)}

        for a, b in prerequisites:
            adj[a].append(b)
            revAdj[b].append(a)

        output = []

        #dfs that returns true if there is a path to searchedFor from curr
        def dfs(curr, searchedFor, seen):
            if curr == searchedFor:
                return True
  
            if curr in seen:
                return False

            seen.add(curr)

            for nei in revAdj[curr]:
                if dfs(nei, searchedFor, seen):
                    return True

            return False

  
        for a, b in queries:
            if b in adj[a]:
                output.append(True)
            else:
                #is there a path in our reverseGraph that reaches a from b
                #if so true else false
                output.append(dfs(b, a, set()))

        return output
```
###### Programming Language Utilized:

- [[Python]]
###### Data structure utilized:
- [[Graphs]]
- [[depth first search]]
- [[Topological Sort]]
#### Important Subdetails

- We adapt Kahn's algorithm/topological sort to our needs, we need to keep track of a node’s prerequisites. Instead of just processing nodes in topological order, we'll modify the algorithm to maintain a list of dependencies for each node. As we move from node `u` to node `v`, we’ll add all of `u`'s prerequisites to `v`'s prerequisites. This is important because it computes the transitive closure, meaning we’re not just tracking immediate dependencies, but also indirect ones.
- By the end of this process, each node will have a complete list of all nodes that must be visited before it. With this setup, when we need to answer a query `(u, v)`, all we have to do is check if `u` is in the list of prerequisites for `v`.
#### Runtime of Optimal Solution

- Kahn's algorithm runs O(n^3 + q) where n is number of courses and q is the size of the queries list
- adjlist creation takes O(n^2) as we iterate over prereqs
- Size of hte indegree array is O(n)
- We iterate over every edge and vertex which is O(n^2) or O(V + E)
- for each edge we also add prereqs to the  next node which is O(N)
- to answer each query we need constant time to retrieve from the map so O(Q)
- space complexity is O(n^2) as we store every edge in the prereqs list
---
Links :: [[#Example Code]] [[Computer Science]] [[Leetcode Daily Contests]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2025-01-26 20:44
