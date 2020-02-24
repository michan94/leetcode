## Problem

Implement strStr().

Return the index of the first occurrence of needle in haystack, or -1 if needle is not part of haystack.

### Example 1:

Input: haystack = "hello", needle = "ll"

Output: 2

### Example 2:

Input: haystack = "aaaaa", needle = "bba"

Output: -1

**First Solution:**
```python
class Solution(object):
    def strStr(self, haystack, needle):
        """
        :type haystack: str
        :type needle: str
        :rtype: int
        """
        if len(needle) == 0:
            return 0;
        index = 0
        lenNeedle = len(needle);
        while index <= (len(haystack) - lenNeedle):
            if haystack[index] == needle[0]:
                substr = haystack[index:index + lenNeedle];
                if needle == substr:
                    return index;
            index += 1;
        return -1;
```