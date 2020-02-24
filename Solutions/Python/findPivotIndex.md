## Problem

Given an array of integers nums, write a method that returns the "pivot" index of this array.

We define the pivot index as the index where the sum of the numbers to the left of the index is equal to the sum of the numbers to the right of the index.

If no such index exists, we should return -1. If there are multiple pivot indexes, you should return the left-most pivot index.

**First Solution:**
```python
class Solution(object):
    def pivotIndex(self, nums):
        """
        :type nums: List[int]
        :rtype: int
        """
        if len(nums) < 3:
            return -1;
        else:
            pivot = 1;
            lSum = 0;
            rSum = 0;
            for num in nums:
                rSum += num;
            #Index 0
            rSum -= nums[0]
            if rSum == 0:
                return 0;
            #Rest of list
            while pivot < (len(nums) - 1):
                lSum += nums[pivot - 1]
                rSum -= nums[pivot]
                print("lSum is: " + str(lSum))
                print("rSum is: " + str(rSum))
                if lSum == rSum:
                    return pivot;
                pivot += 1;
            #Index len(nums)
            #Dont want this before previous while loop because want leftmost index in tie
            lSum += nums[-2]
            rSum = 0
            if lSum == rSum:
                return pivot
        return -1;
```