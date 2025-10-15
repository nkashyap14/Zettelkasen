# Binary Tree Preorder Iterative Traversal

#### Pattern statement

- Traverses a [[binary tree]] in a pre order manner. Pre order meaning that first some work is conducted on the root node. Then we go traverse the subtrees. Normally going to left sub tree first and then right subtree.
- Fundamentally this is a [[depth first search]] algorithm
- This is an [[iterative]] implementation

##### Implementation
```
class TreeNode:
	def __init__(self, val=0, left=None, right=None):
		self.val = val
		self.left = left
		self.right = right

def inorderTraversal(self, root: Optional[TreeNode]) -> List[int]:
	if not root:
		return []
	stk, out = [root], []
	
	while stk:
		cur = stk.pop()
		
		output.append(cur.val)
		
		if cur.right:
			stk.append(cur.right)
		if cur.left:
			stk.append(cur.left)
			
	return out
```

###### Programming Language Utilized:

[[Python]]

#### Runtime + Space Complexity

- O(n) runtime
- O(n) space complexity worst case
	- Worst case comes in the preorder case from having many right children that we have to save on our path to the leaf nodes which can grow the stack up to n/2
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
