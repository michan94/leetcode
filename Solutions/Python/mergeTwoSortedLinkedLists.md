## Problem

Merge two sorted linked lists and return it as a new list. The new list should be made by splicing together the nodes of the first two lists.

**First Solution:**
```python
# Definition for singly-linked list.
# class ListNode(object):
#     def __init__(self, x):
#         self.val = x
#         self.next = None

class Solution(object):
    def mergeTwoLists(self, l1, l2):
        result = ListNode(0);
        curr = result;
        while (l1 != None and l2 != None):
            if l1.val <= l2.val:
                curr.next = l1;
                l1 = l1.next;
            else:
                curr.next = l2;
                l2 = l2.next;
            curr = curr.next;
        if l1 is None:
            curr.next = l2;
        if l2 is None:
            curr.next = l1;
        return result.next;		#Returns the linked list starting after the dummy node ListNode(0)
```