# Subtree Of Another Tree

#### Problem statement
Given the roots of two binary trees `root` and `subRoot`, return `true` if there is a subtree of `root` with the same structure and node values of `subRoot` and `false` otherwise.

A subtree of a binary tree `tree` is a tree that consists of a node in `tree` and all of this node's descendants. The tree `tree` could also be considered as a subtree of itself.

##### Example 1
```
Input: root = [1,2,3,4,5], subRoot = [2,4,5]

Output: true
```
##### Example 2
```
Input: root = [1,2,3,4,5,null,null,6], subRoot = [2,4,5]

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
    def isSubtree(self, root: Optional[TreeNode], subRoot: Optional[TreeNode]) -> bool:
        def dfs(root, subroot):
            if not root and not subroot:
                return True
            if root and subroot and root.val == subroot.val:
                return dfs(root.left, subroot.left) and dfs(root.right, subroot.right)
            return False

        q = []
        q.append(root)
        while q:
            node = q.pop(0)

            if node.val == subRoot.val:
                truth = dfs(node, subRoot)
                if truth:
                    return True
            if node.left:
                q.append(node.left)
            if node.right:
                q.append(node.right)

        return False
```
#### Solution 2
```
class Solution:
    def isSubtree(self, root: Optional[TreeNode], subRoot: Optional[TreeNode]) -> bool:
        if not subRoot:
            return True
        if not root:
            return False

        if self.sameTree(root, subRoot):
            return True
        return self.isSubtree(root.left, subRoot) or self.isSubtree(root.right, subRoot)

    def sameTree(self, root: Optional[TreeNode], subRoot: Optional[TreeNode]) -> bool:
        if not root and not subRoot:
            return True
        if root and subRoot and root.val == subRoot.val:
            return self.sameTree(root.left, subRoot.left) and self.sameTree(root.right, subRoot.right)
        return False
```
###### Programming Language Utilized:

###### Data structure utilized:
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
Date :: 2024-10-08 08:06
