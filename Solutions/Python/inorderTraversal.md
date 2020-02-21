## Problem

Given a binary tree, return the inorder traversal of its nodes' values.

### Example:

Input: [1,null,2,3]


   1

    \

     2

    /

   3

Output: [1,3,2]

**First Solution:**
```python
# Definition for a binary tree node.
# class TreeNode(object):
#     def __init__(self, x):
#         self.val = x
#         self.left = None
#         self.right = None

class Solution(object):
    def inorderTraversal(self, root):
        """
        :type root: TreeNode
        :rtype: List[int]
        """
        result = [];
        if root is None:
            return [];
        else:
            result.extend(self.inorderTraversal(root.left));
            result.append(root.val);
            result.extend(self.inorderTraversal(root.right));
        return result;
```