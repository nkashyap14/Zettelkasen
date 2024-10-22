# Remove Nth Node From End of List

#### Problem statement
You are given the beginning of a linked list `head`, and an integer `n`.

Remove the `nth` node from the end of the list and return the beginning of the list.

##### Example 1
```
Input: head = [1,2,3,4], n = 2

Output: [1,2,4]
```
##### Example 2
```
Input: head = [5], n = 1

Output: []
```
#### Solution
```
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next

  

class Solution:
    def removeNthFromEnd(self, head: Optional[ListNode], n: int) -> Optional[ListNode]:
        dummyNode = ListNode(0, head)
        l, r = dummyNode, head
        #establishing a n + 1 gap between l and r. + 1 because we point l to the dummy node
        while n > 0:
            right = right.next
            n = n - 1
        #continue iterating over the linked list until right is at None aka at the end of the list. thats when
        #we know left is at the node before the nth node from the end of the list

        while right:
            right = right.next
            left = left.next
        #just point n to the node after its next node
        left.next = left.next.next
        #return the head of the list

        return dummyNode.next
```

###### Programming Language Utilized:
- [[Python]]
###### Data structure utilized:

- [[Linked List]]
#### Important Subdetails

- [[Two Pointers]] is commonly utilized
	- Sometimes fast, and slow pointer
	- this time its two pointers but we just establish a certain amount of node gap in between the two pointers
#### Runtime of Optimal Solution

- O(N) time complexity
- O(1) space ccomplexity
---
Links :: [[#Example Code]] [[Computer Science]] [[Neetcode 150]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-10-10 11:50
