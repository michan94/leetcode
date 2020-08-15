## Problem

Given the array candies and the integer extraCandies, where candies[i] represents the number of candies that the ith kid has.

For each kid check if there is a way to distribute extraCandies among the kids such that he or she can have the greatest number of candies among them. Notice that multiple kids can have the greatest number of candies. 

### Example 1:

Input: candies = [2,3,5,1,3], extraCandies = 3

Output: [true,true,true,false,true] 

### Example 2:

Input: candies = [4,2,1,1,2], extraCandies = 1

Output: [true,false,false,false,false] 

### Example 3:

Input: candies = [12,1,12], extraCandies = 10

Output: [true,false,true]


**First Solution:**
```python
class Solution(object):
    def kidsWithCandies(self, candies, extraCandies):
        """
        :type candies: List[int]
        :type extraCandies: int
        :rtype: List[bool]
        """
        result = []
        most = max(candies)
        for kid in candies:
            if kid + extraCandies >= most:
                result.append(True)
            else:
                result.append(False)
        return result
```