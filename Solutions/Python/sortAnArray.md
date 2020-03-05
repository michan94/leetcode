## Problem

Given an array of integers nums, sort the array in ascending order.

### Example 1:

Input: nums = [5,2,3,1]

Output: [1,2,3,5]

### Example 2:

Input: nums = [5,1,1,2,0,0]

Output: [0,0,1,1,2,5]

**First Solution:**
```python
#Merge Sort Solution

class Solution(object):
    def sortArray(self, nums):
        """
        :type nums: List[int]
        :rtype: List[int]
        """
        if len(nums) <= 1:
            return nums;
        pivot = len(nums)/2
        left = self.sortArray(nums[0:pivot]);
        right = self.sortArray(nums[pivot:]);
        return self.merge(left, right)
    
    def merge(self, left, right):
        leftCursor = 0
        rightCursor = 0;
        result = [];
        while leftCursor < len(left) and rightCursor < len(right):
            if left[leftCursor] < right[rightCursor]:
                result.append(left[leftCursor]);
                leftCursor += 1;
            else:
                result.append(right[rightCursor]);
                rightCursor += 1;
        result.extend(left[leftCursor:]);
        result.extend(right[rightCursor:]);
        return result;
```

