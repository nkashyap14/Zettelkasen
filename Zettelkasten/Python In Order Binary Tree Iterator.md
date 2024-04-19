# Python In Order Binary Tree Iterator

```
class InorderIterator:
    def __init__(self, root):
        self.vals = self.getVals(root, [])
        pass
        
    def hasNext(self):
        return len(self.vals) > 0
        pass
        
    def getNext(self):
        if len(self.vals) == 0:
            return None
        //note have to specify 0 index to pop from otherwise the last value gets popped
        val = self.vals.pop(0)
        return val
        
    def getVals(self, root, vals):
        if not root:
            return vals
        self.getVals(root.left, vals)
        vals.append(root)
        self.getVals(root.right, vals)
        return vals

def inorder_using_iterator(root):
    iter = InorderIterator(root)
    result = ""
    while iter.hasNext():
        ptr = iter.getNext()
        result += str(ptr.data) + " "
    return result
```
![[binary_trees_inorder_iteration.jpg]]
#### Runtime Complexity
- [[O(N)]] as every node needs to be touched
#### Memory Complexity
- O(h) where h is the height of the tree. [[call stack|Stack]] needs to be instantiated to store info on the tree up to the height.

---
Links :: [[#Example Code]] [[Computer Science]] [[Python]] [[binary tree]] [[In order traversal]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-04-04 23:51
