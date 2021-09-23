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

**Second Solution:**
```python
class Solution(object):
    def twoSum(self, numbers, target):
        """
        :type numbers: List[int]
        :type target: int
        :rtype: List[int]
        """
        result = [];
        for i in range(len(numbers)-1):
            missing = target - numbers[i];
            for j in range(i+1, len(numbers)):
                if numbers[j] == missing:
                    result.append(i + 1);
                    result.append(j + 1);
        return result;
```


**Third Solution:**
```python
class Solution(object):
    def twoSum(self, nums, target):
        """
        :type nums: List[int]
        :type target: int
        :rtype: List[int]
        """
        if len(nums) < 2:
            return [-1,-1]
        left = 0
        right = 1
        while left < len(nums) - 1:
            while right < len(nums):
                if nums[left] + nums[right] == target:
                    return [left, right]
                else:
                    right += 1
            left += 1
            right = left + 1
        return [-1, -1]
```
