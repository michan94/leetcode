## Problem

Given two sorted integer arrays nums1 and nums2, merge nums2 into nums1 as one sorted array.

Note:

The number of elements initialized in nums1 and nums2 are m and n respectively.

You may assume that nums1 has enough space (size that is greater or equal to m + n) to hold additional elements from nums2.

###Example:

Input:

nums1 = [1,2,3,0,0,0], m = 3

nums2 = [2,5,6],       n = 3

Output: [1,2,2,3,5,6]

**First Solution:**
```python
class Solution(object):
    def merge(self, nums1, m, nums2, n):
        """
        :type nums1: List[int]
        :type m: int
        :type nums2: List[int]
        :type n: int
        :rtype: None Do not return anything, modify nums1 in-place instead.
        """
        l1 = m - 1
        l2 = n - 1
        end = m + n - 1
        while l1 >= 0 and l2 >= 0:
            if nums1[l1] > nums2[l2]:
                nums1[end]  = nums1[l1]
                l1 -= 1
            else:
                nums1[end] = nums2[l2]
                l2 -= 1
            end -= 1
        # l1 is empty
        if l1 < 0:
            nums1[:l2 + 1] = nums2[:l2 + 1]
        
        #Dont need to do anything if l2 is empty since l1 already in order from beginning of list
```