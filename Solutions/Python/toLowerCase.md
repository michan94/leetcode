## Problem

Implement function ToLowerCase() that has a string parameter str, and returns the same string in lowercase.


**First Solution:**
```python
class Solution(object):
    def toLowerCase(self, str):
        """
        :type str: str
        :rtype: str
        """
        result = "";
        for letter in str:
            if letter == letter.upper():
                result += letter.lower();
            else:
                result += letter;
        return result;
```