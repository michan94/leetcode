## Problem

Given a binary tree, return the postorder traversal of its nodes' values.

### Example:

Input: [1,null,2,3]


   1

    \

     2

    /

   3

Output: [3,2,1]

**First Solution:**
```python
# Definition for a binary tree node.
# class TreeNode(object):
#     def __init__(self, x):
#         self.val = x
#         self.left = None
#         self.right = None

class Solution(object):
    def postorderTraversal(self, root):
        """
        :type root: TreeNode
        :rtype: List[int]
        """
        result = [];
        if root is None:
            return [];
        else:
            result.extend(self.postorderTraversal(root.left));
            result.extend(self.postorderTraversal(root.right));
            result.append(root.val);
        return result
```