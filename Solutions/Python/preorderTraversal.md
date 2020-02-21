## Problem

Given a binary tree, return the preorder traversal of its nodes' values.

### Example:

Input: [1,null,2,3]

   1
   
    \
    
    
     2
    
    /
    
   3

Output: [1,2,3]

**First Solution:**
```python
# Definition for a binary tree node.
# class TreeNode(object):
#     def __init__(self, x):
#         self.val = x
#         self.left = None
#         self.right = None

class Solution(object):
    def preorderTraversal(self, root):
        """
        :type root: TreeNode
        :rtype: List[int]
        """
        result = []
        if root is None:        #Empty Node
            return [];
        else:  
            result.append(root.val);
            result.extend(self.preorderTraversal(root.left ));
            result.extend(self.preorderTraversal(root.right));
        return result;
```