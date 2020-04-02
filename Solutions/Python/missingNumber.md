## Problem

Given an array containing n distinct numbers taken from 0, 1, 2, ..., n, find the one that is missing from the array.

### Example 1:

Input: [3,0,1]

Output: 2

### Example 2:

Input: [9,6,4,2,3,5,7,0,1]

Output: 8

**First Solution:**
```python
class Solution(object):
    def missingNumber(self, nums):
        """
        :type nums: List[int]
        :rtype: int
        """
        if len(nums) < 1:
            return -1
        temp = []
        numbers = sorted(nums)
        n = numbers[-1]
        for i in range(n + 1):
            if i in numbers:
                numbers.remove(i)
            else:
                return i
        if len(numbers) == 0:
            return n + 1
```

