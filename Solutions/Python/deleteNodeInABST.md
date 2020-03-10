## Problem

Given a root node reference of a BST and a key, delete the node with the given key in the BST. Return the root node reference (possibly updated) of the BST.

Basically, the deletion can be divided into two stages:

Search for a node to remove.

If the node is found, delete the node.

Note: Time complexity should be O(height of tree).

### Example:

root = [5,3,6,2,4,null,7]

key = 3

    5

   / \

  3   6

 / \   \

2   4   7


Given key to delete is 3. So we find the node with value 3 and delete it.

One valid answer is [5,4,6,2,null,null,7], shown in the following BST.

    5

   / \

  4   6

 /     \

2       7

Another valid answer is [5,2,6,null,4,null,7].

    5

   / \

  2   6

   \   \

    4   7


**First Solution:**
```python
# Definition for a binary tree node.
# class TreeNode(object):
#     def __init__(self, x):
#         self.val = x
#         self.left = None
#         self.right = None

class Solution(object):
    def deleteNode(self, root, key):
        """
        :type root: TreeNode
        :type key: int
        :rtype: TreeNode
        """
        if root is None: 
            return None
        if root.val > key:
            root.left = self.deleteNode(root.left, key);
        elif root.val < key:
            root.right = self.deleteNode(root.right, key);
        #root.val == key
        else:
            if root.left is not None:
                # Find the right most leaf of the left sub-tree
                left_right_most = root.left
                while left_right_most.right is not None:
                    left_right_most = left_right_most.right
                # Attach right child to the right of that leaf
                left_right_most.right = root.right
                # Return left child instead of root, a.k.a delete root
                return root.left
            else:
                return root.right
        return root
```
