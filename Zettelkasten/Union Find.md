# Union Find

# Union Find (Disjoint Set Union)

## Definition

Union Find is a data structure that tracks a collection of elements partitioned into disjoint (non-overlapping) sets. It supports two primary operations:

- find(): Determine which subset an element belongs to
- union(): Join two subsets into a single subset


- Union find starts off as a forest of trees where each tree's node is parent of itself
- As you go through edges connect those tree's
	- Everytime you merge your n components gets decremented by one
- Also maintain a rank of the connected components
	- Size in most cases
- When merging find the root parent of both components. Connect to the one whose rank is bigger
- Only do a union operation when both components you are connecting don't have the same root parent
## Core Operations & Complexity

- Initialization: O(n)
- find(): O(α(n)) ≈ O(1) with path compression
- union(): O(α(n)) ≈ O(1) with rank/size optimization Where α(n) is the inverse Ackermann function, which grows extremely slowly

## Common Optimizations

1. Path Compression: Make each node point directly to root during find()
2. Union by Rank/Size: Attach smaller tree to root of larger tree

#### Pseudocode

```
- Initialize with Parent[i] = i
function find(x):
	#if the parent of x isn't itself then we know we haven't reached the root of the tree
	if Parent[x] != x:
		return find(Parent[x])
	else:
		return x

function union(x, y):
	#find the root of y and x. set the parent of root of y to the root of x which joins the two up until this point unconnected components together
	Parent[find(y)] = find(x)

```

## Template Implementation

```
class UnionFind:
    def __init__(self, size):
        self.parent = [i for i in range(size)]
        self.rank = [1] * size
    
    def find(self, x):
        while x != self.parent[x]:
            self.parent[x] = self.parent[self.parent[x]]  # Path compression
            x = self.parent[x]
        return x
    
    def union(self, x, y):
        px, py = self.find(x), self.find(y)
        if px == py: return False  # Already in same set
        
        # Union by rank
        if self.rank[px] > self.rank[py]:
            self.parent[py] = px
            self.rank[px] += self.rank[py]
        else:
            self.parent[px] = py
            self.rank[py] += self.rank[px]
        return True
```

## Problem Types

1. Connected Components Problems
    - Finding cycles in graphs
    - Detecting redundant connections
    - Minimum spanning trees
	- [[Number of Connected Components in an Undirected Graph]]
1. Dynamic Connectivity
    - Network connectivity
    - Social networks (friend circles)
    - Grid/matrix connectivity
2. Equivalence Relationship Problems
    - Account merging
    - Similar strings grouping
    - Connected regions

## Key Characteristics

- Initially, each element is in its own set
- Sets are represented as tree structures
- The root of each tree is the set's representative
- Operations modify tree structure to maintain set relationships

## When to Use

Use Union Find when you need to:

1. Track groups of connected elements
2. Efficiently check if two elements are connected
3. Merge connected components
4. Find cycles in undirected graphs
5. Handle dynamic connectivity queries

## Space Complexity

- O(n) where n is number of elements
- Time complexity is O(n) without path compression or O(a(n)) without path compression where a(n) is the [[Reverse Ackermann Function]]

---
Links :: [[Computer Science]] [[Zettelkasten/Algorithm]] [[Algorithmic Technique]] [[Graph]]
Reference ::
Type :: #atom
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-12-05 06:25
