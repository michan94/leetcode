## Problem

You are given a sorted array consisting of only integers where every element appears exactly twice, except for one element which appears exactly once. Find this single element that appears only once.

Follow up: Your solution should run in O(log n) time and O(1) space.

### Example 1:

Input: nums = [1,1,2,3,3,4,4,8,8]

Output: 2

### Example 2:

Input: nums = [3,3,7,7,10,11,11]

Output: 10

**First Solution:**
```python
class Solution(object):
    def singleNonDuplicate(self, nums):
        """
        :type nums: List[int]
        :rtype: int
        """
        if len(nums) < 1:
            return -1
        temp = {}
        for num in nums:
            if num in temp:
                temp[num] += 1
            else:
                temp[num] = 1
        for key, value in temp.items():
            if value == 1:
                return key
```