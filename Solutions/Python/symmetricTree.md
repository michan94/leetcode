## Problem

Given a binary tree, check whether it is a mirror of itself (ie, symmetric around its center).

For example, this binary tree [1,2,2,3,4,4,3] is symmetric:

    1

   / \

  2   2

 / \ / \

3  4 4  3
 

But the following [1,2,2,null,3,null,3] is not:

    1

   / \

  2   2

   \   \

    3    3

**First Solution:**
```python
# Definition for a binary tree node.
# class TreeNode(object):
#     def __init__(self, x):
#         self.val = x
#         self.left = None
#         self.right = None

class Solution(object):
    def isSymmetric(self, root):
        """
        :type root: TreeNode
        :rtype: bool
        """
        def symmetric(left, right):
            if left is None and right is None:
                return True;
            if left is not None and right is not None and left.val == right.val:
                return symmetric(left.left, right.right) and symmetric(left.right,                     right.left)
            return False
        return symmetric(root, root)
                
```