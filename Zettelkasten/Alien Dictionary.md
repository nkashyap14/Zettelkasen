# Alien Dictionary

#### Problem statement

There is a foreign language which uses the latin alphabet, but the order among letters is _not_ "a", "b", "c" ... "z" as in English.

You receive a list of _non-empty_ strings `words` from the dictionary, where the words are **sorted lexicographically** based on the rules of this new language.

Derive the order of letters in this language. If the order is invalid, return an empty string. If there are multiple valid order of letters, return **any** of them.

A string `a` is lexicographically smaller than a string `b` if either of the following is true:

- The first letter where they differ is smaller in `a` than in `b`.
- There is no index `i` such that `a[i] != b[i]` _and_ `a.length < b.length`.
##### Example 1
```
Input: ["z","o"]

Output: "zo"
```
##### Example 2
```
Input: ["hrn","hrf","er","enn","rfnn"]

Output: "hernf"
```
#### Solution 1: Depth First Search
```
class Solution:
    def foreignDictionary(self, words: List[str]) -> str:
        adj = {c: set() for w in words for c in w}

        for i in range(len(words) - 1):
            w1, w2 = words[i], words[i + 1]
            minLen = min(len(w1), len(w2))
            if len(w1) > len(w2) and w1[:minLen] == w2[:minLen]:
                return ""

            for j in range(minLen):
                if w1[j] != w2[j]:
                    adj[w1[j]].add(w2[j])
                    break

        visit = {} #nodes mapped to false or true. False means its visisted. true means its visited and its in the current path
        #if its not in visit means it hasnt been visited

        res = []

        def dfs(c):
            if c in visit:
                #if it returns true we have a cycle
                return visit[c]

            #character is in path
            visit[c] = True
            
            for nei in adj[c]:
                #we have detected a cycle so return true
                if dfs(nei):
                    return True


            #visited but not in path
            visit[c] = False
            res.append(c)


        for char in adj:
            #if we have a cycle then there is valid ordering so return empty string
            if dfs(char):
                return ""

        res.reverse()

        return "".join(res)

```


#### Solution 2: Topological Sort

```
class Solution:
    def foreignDictionary(self, words: List[str]) -> str:

        adj = {c: set() for w in words for c in w}
        indegree = {c: 0 for c in adj}

        for i in range(len(words) - 1):
            w1, w2 = words[i], words[i + 1]
            minLen = min(len(w1), len(w2))
            if len(w1) > len(w2) and w1[:minLen] == w2[:minLen]:
                return ""

            for j in range(minLen):
                if w1[j] != w2[j]:
                    if w2[j] not in adj[w1[j]]:
                        #the character in the earlier world precedes the character in word 2
                        adj[w1[j]].add(w2[j])
                        #the characte rin second word has an incoming connection
                        indegree[w2[j]] += 1
                    break
        
        q = deque([c for c in indegree if indegree[c] == 0])
        res = []

        while q:
            char = q.popleft()
            res.append(char)

            for neighbor in adj[char]:
                indegree[neighbor] -= 1
                if indegree[neighbor] == 0:
                    q.append(neighbor)

        if len(res) != len(indegree):
            return ""

        return "".join(res)
```
###### Programming Language Utilized:

- [[Python]]
###### Data structure utilized:

- [[Graphs]]
- [[Advanced Graphs]]
- [[depth first search]]
- [[Topological Sort]]
#### Important Subdetails

#### Runtime of Optimal Solution

- O(N + V + E) runtime where V is number of unique characters, E is edges, and N is the sum of all the lengths of the strings
- O(V + E) space complexity
- For both algorithms
---
Links :: [[#Example Code]] [[Computer Science]] [[Neetcode 150]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2025-01-27 12:21
