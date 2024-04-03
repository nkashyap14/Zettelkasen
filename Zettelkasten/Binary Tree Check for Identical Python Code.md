# Binary Tree Identical Python

```
def are_identical(root1, root2):
	if not root1 and not root2:
		return True
	if not root1 or not root2:
		return False
	if root1.data != root2.data:
		return False

	return are_identical(root1.left, root2.left) and are_identical(root1.right, root2.right)
	
```
#### Runtime Complexity
- Linear: O(n) as we have to iterate over every node in the tree of size n
#### Memory Complexity
- O(h) where h is the height of the [[binary tree]]. Reason is the recursive solution consumes memory on the [[stack]] up to the height of the binary tree
- 
![[python_binary_trees_identical.jpg]]
---
Links :: [[#Example Code]] [[Computer Science]] [[Python]] [[Data Structures]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-04-02 23:09
