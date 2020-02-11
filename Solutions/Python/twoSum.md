## Problem

Given an array of integers, return indices of the two numbers such that they add up to a specific target.

You may assume that each input would have exactly one solution, and you may not use the same element twice.

**First Solution:**
```python
class Solution(object):
    def twoSum(self, nums, target):
        result = [];
        index = 0;
        for num in nums:
            need = target - num;
            tmp = nums[nums.index(num):];
            if need in tmp:
                return [nums.index(num), tmp.index(need) + nums.index(num)]
```