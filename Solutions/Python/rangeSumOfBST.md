## Problem

Given the root node of a binary search tree, return the sum of values of all nodes with value between L and R (inclusive).

The binary search tree is guaranteed to have unique values.

 

### Example 1:

Input: root = [10,5,15,3,7,null,18], L = 7, R = 15

Output: 32

### Example 2:

Input: root = [10,5,15,3,7,13,18,1,null,6], L = 6, R = 10

Output: 23


**First Solution:**
```python
# Definition for a binary tree node.
# class TreeNode(object):
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution(object):
    def rangeSumBST(self, root, L, R):
        """
        :type root: TreeNode
        :type L: int
        :type R: int
        :rtype: int
        """
        total = 0
        if root is None:
            return 0
        if root.val >= L and root.val <= R:
            total += root.val
        return total + self.rangeSumBST(root.left, L, R) + self.rangeSumBST(root.right, L, R)
```