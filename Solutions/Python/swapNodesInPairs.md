## Problem

Given a linked list, swap every two adjacent nodes and return its head.

You may not modify the values in the list's nodes, only nodes itself may be changed.

**First Solution:**
```python
# Definition for singly-linked list.
# class ListNode(object):
#     def __init__(self, x):
#         self.val = x
#         self.next = None

class Solution(object):
    def swapPairs(self, head):
        """
        :type head: ListNode
        :rtype: ListNode
        """
        if (head is not None) and (head.next is not None):
            temp = head.next;
            nextHead = head.next.next;
            head.next = self.swapPairs(nextHead);
            temp.next = head;
            return temp;
        else:
            return head;
```