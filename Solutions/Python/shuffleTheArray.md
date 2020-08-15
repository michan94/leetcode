## Problem

Given the array nums consisting of 2n elements in the form [x1,x2,...,xn,y1,y2,...,yn].

Return the array in the form [x1,y1,x2,y2,...,xn,yn].

 

### Example 1:

Input: nums = [2,5,1,3,4,7], n = 3

Output: [2,3,5,4,1,7] 


**First Solution:**
```python
class Solution(object):
    def shuffle(self, nums, n):
        """
        :type nums: List[int]
        :type n: int
        :rtype: List[int]
        """
        i = 0
        x = 0
        result = []
        while i < len(nums):
            if i % 2 == 0:
                result.append(nums[x])
                x += 1
            else:
                result.append(nums[n])
                n += 1
            i += 1
        return result
        
```