# Binary Tree Diameter

#### Problem statement
The **diameter** of a binary tree is defined as the **length** of the longest path between _any two nodes within the tree_. The path does not necessarily have to pass through the root.

The **length** of a path between two nodes in a binary tree is the number of edges between the nodes.

Given the root of a binary tree `root`, return the **diameter** of the tree.
##### Example 1
```
Input: root = [1,null,2,3,4,5]

Output: 3
```
##### Example 2
```
Input: root = [1,2,3]

Output: 2
```
#### Solution
```
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right

  

class Solution:
    def diameterOfBinaryTree(self, root: Optional[TreeNode]) -> int:
        res = 0
        def dfs(root):
            nonlocal res
            if not root:
                return 0
            left = dfs(root.left)
            right = dfs(root.right)

			#this is the diameter calculation
            res = max(res, left + right)

			#this is the height calculation
            return 1 + max(left, right)
        dfs(root)
        return res
```

###### Programming Language Utilized:
- [[Python]]
###### Data structure utilized:

- [[Binary Tree]]
- [[Recursion]]
#### Important Subdetails

- [[Python nonlocal]] is used as a way to make the res variable in the inner recursive function the same res in the outer function
- The principle of this is that the recursive function works by just outputting the height of the tree while the res nonlocal variable is used to track our return value which is the diameter which in reality should be the height of the left and the right subtree added together
	- Obviously we are maximizing res so we only set it to res if its actually greater
#### Runtime of Optimal Solution

- O(n) as it is a [[depth first search]] that touches every node in the tree
- Space complexity O(log n) in the case of a [[balanced tree]] while it can be O(n) in the case of an [[unbalanced tree]]
---
Links :: [[#Example Code]] [[Computer Science]] [[Neetcode 150]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-10-07 17:47
