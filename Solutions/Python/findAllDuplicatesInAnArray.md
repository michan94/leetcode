## Problem

Given an array of integers, 1 ≤ a[i] ≤ n (n = size of array), some elements appear twice and others appear once.

Find all the elements that appear twice in this array.

Could you do it without extra space and in O(n) runtime?

### Example:

Input:

[4,3,2,7,8,2,3,1]

Output:

[2,3]


**First Solution:**
```python
class Solution(object):
    def findDuplicates(self, nums):
        """
        :type nums: List[int]
        :rtype: List[int]
        """
        cache = {}
        temp = []
        for num in nums:
            if num in cache:
                cache[num] += 1
            else:
                cache[num] = 1
        for key, value in cache.items():
            if value == 2:
                temp.append(key)
        return temp
```