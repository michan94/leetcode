## Problem

Given an array of integers, return indices of the two numbers such that they add up to a specific target.

You may assume that each input would have exactly one solution, and you may not use the same element twice.

**First Solution:**
```python
class Solution(object):
    def twoSum(self, nums, target):
        for num in nums:
            need = target - num;
            tmpIndex = nums.index(num) + 1;
            tmp = nums[tmpIndex:];
            if need in tmp:
                return [nums.index(num), tmpIndex + tmp.index(need)]
```