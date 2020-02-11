## Problem

Given an array nums of integers, return how many of them contain an even number of digits.

**First Solution:**
```python
class Solution(object):
    def findNumbers(self, nums):
        """
        :type nums: List[int]
        :rtype: int
        """
        total = 0;
        for num in nums:
            count = 0;
            num = str(num);
            for digit in num:
                count += 1;
            if count % 2 == 0:
                total += 1;
        return total;
```
