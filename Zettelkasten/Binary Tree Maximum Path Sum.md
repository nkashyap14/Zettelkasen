# Binary Tree Maximum Path Sum

#### Problem statement

Given the `root` of a _non-empty_ binary tree, return the maximum **path sum** of any _non-empty_ path.

A **path** in a binary tree is a sequence of nodes where each pair of adjacent nodes has an edge connecting them. A node can _not_ appear in the sequence more than once. The path does _not_ necessarily need to include the root.

The **path sum** of a path is the sum of the node's values in the path.
##### Example 1
```
Input: root = [1,2,3]

Output: 6
```
##### Example 2
```
Input: root = [-15,10,20,null,null,15,5,-5]

Output: 40
```
#### Solution
```
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right

class Solution:
    def maxPathSum(self, root: Optional[TreeNode]) -> int:

        self.res = root.val

        def dfs(root):

            if not root:
                return 0

            #get the maximum path sum we can get by traversing left
            #without splitting
            leftMax = max(dfs(root.left), 0)
            #get the maximum path sum we can get by traversing right
            #without splitting
            rightMax = max(dfs(root.right), 0)

            #check if splitting from this node can give us the max value
            self.res = max(self.res, root.val + leftMax + rightMax)

            #maximum value we can get from this node without splitting
            return root.val + max(leftMax, rightMax)

        dfs(root)

        return self.res
```

###### Programming Language Utilized:

- [[Python]]
###### Data structure utilized:

- [[Binary Tree]]
- [[Post Order Traversal]]
#### Important Subdetails

#### Runtime of Optimal Solution

- O(n) runtime
- O(n) worstcase space complexity
---
Links :: [[#Example Code]] [[Computer Science]] [[Neetcode 150]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2025-01-27 12:46
