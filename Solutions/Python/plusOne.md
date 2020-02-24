## Problem

Given a non-empty array of digits representing a non-negative integer, plus one to the integer.

The digits are stored such that the most significant digit is at the head of the list, and each element in the array contain a single digit.

You may assume the integer does not contain any leading zero, except the number 0 itself.

### Example 1:

Input: [1,2,3]

Output: [1,2,4]

Explanation: The array represents the integer 123.

### Example 2:

Input: [4,3,2,1]

Output: [4,3,2,2]

Explanation: The array represents the integer 4321.

**First Solution:**
```python
class Solution(object):
    def plusOne(self, digits):
        """
        :type digits: List[int]
        :rtype: List[int]
        """
        tmp = ""
        result = [];
        for digit in digits:
            tmp += str(digit);
        tmp = int(tmp) + 1;
        tmp = str(tmp);
        for digit in tmp:
            result.append(digit);
        for digit in result:
            digit = int(digit);
        return result;
```