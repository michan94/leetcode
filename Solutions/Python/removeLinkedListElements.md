## Problem

Remove all elements from a linked list of integers that have value val.

### Example:

Input:  1->2->6->3->4->5->6, val = 6

Output: 1->2->3->4->5


**First Solution:**
```python
# Definition for singly-linked list.
# class ListNode(object):
#     def __init__(self, x):
#         self.val = x
#         self.next = None

class Solution(object):
    def removeElements(self, head, val):
        """
        :type head: ListNode
        :type val: int
        :rtype: ListNode
        """
        temp = ListNode(0);
        temp.next = head;
        curr = temp;
        while curr.next is not None:
            if curr.next.val == val:
                curr.next = curr.next.next;
            else:
                curr = curr.next;
        return temp.next;
```