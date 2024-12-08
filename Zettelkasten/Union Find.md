# Union Find

# Union Find (Disjoint Set Union)

## Definition

Union Find is a data structure that tracks a collection of elements partitioned into disjoint (non-overlapping) sets. It supports two primary operations:

- find(): Determine which subset an element belongs to
- union(): Join two subsets into a single subset

## Core Operations & Complexity

- Initialization: O(n)
- find(): O(α(n)) ≈ O(1) with path compression
- union(): O(α(n)) ≈ O(1) with rank/size optimization Where α(n) is the inverse Ackermann function, which grows extremely slowly

## Common Optimizations

1. Path Compression: Make each node point directly to root during find()
2. Union by Rank/Size: Attach smaller tree to root of larger tree

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
2. Dynamic Connectivity
    - Network connectivity
    - Social networks (friend circles)
    - Grid/matrix connectivity
3. Equivalence Relationship Problems
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

O(n) where n is number of elements

---
Links :: [[Computer Science]] [[Algorithm]] [[Algorithmic Technique]] [[Graph]]
Reference ::
Type :: #atom
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-12-05 06:25
