# Binary Tree Preorder Recursive Traversal

#### Pattern statement

- Traverses a [[binary tree]] in a pre order manner. Pre order meaning that first some work is conducted on the root node. Then we go traverse the subtrees. Normally going to left sub tree first and then right subtree.
- Fundamentally this is a [[depth first search]] algorithm

##### Implementation
```
class TreeNode:
	def __init__(self, val=0, left=None, right=None):
		self.val = val
		self.left = left
		self.right = right

def inorderTraversal(self, root: Optional[TreeNode]) -> List[int]:
	def dfs(root):
		if not root:
			return []
			
		return [root.val] + dfs(root.left) + dfs(root.right)
	
	return dfs(root)

```

###### Programming Language Utilized:

#### Runtime + Space Complexity
---
Links :: [[#Example Code]] [[Leetcode]] [[Leetcode Pattern Implementation]] [[Binary Tree]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2025-10-15 16:46
