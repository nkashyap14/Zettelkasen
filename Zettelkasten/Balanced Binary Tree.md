# Balanced Binary Tree

#### Problem statement
Given a binary tree, return `true` if it is **height-balanced** and `false` otherwise.

A **height-balanced** binary tree is defined as a binary tree in which the left and right subtrees of every node differ in height by no more than 1.

##### Example 1
```
Input: root = [1,2,3,null,null,4]

Output: true
```
##### Example 2
```
Input: root = [1,2,3,null,null,4,null,5]

Output: false
```
#### Solution 1
```
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right

class Solution:
    def isBalanced(self, root: Optional[TreeNode]) -> bool:
        if not root:
            return True
        diff = 0
        def dfs(root):
            if not root:
                return 0
            hL = dfs(root.left) + 1
            hR = dfs(root.right) + 1
            nonlocal diff
            diff = max(abs(hL - hR), diff)

            return max(hL, hR)

        dfs(root)
        return diff <= 1
```

#### Solution 2
```
class Solution:
    def isBalanced(self, root: Optional[TreeNode]) -> bool:
	    def dfs(root):
		    if not root:
			    return [True, 0]
	
			left = dfs(root.left)
			right = dfs(root.right)
	
			balanced = left[0] and right[0] and abs(left[1] - right[1]) <= 1
	
			return [balanced, max(left[1], right[1]) + 1]

		return dfs(root)[0]
```
###### Programming Language Utilized:

- [[Python]]
###### Data structure utilized:

- [[binary tree]]
- [[depth first search]]
#### Important Subdetails

#### Runtime of Optimal Solution
- Runtime O(n) as every node is touched in order to calculate height
- Space O(n) for unbalanced and O(log n) for balanced
---
Links :: [[#Example Code]] [[Computer Science]] [[Neetcode 150]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-10-07 19:00
