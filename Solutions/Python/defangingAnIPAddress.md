## Problem

Given a valid (IPv4) IP address, return a defanged version of that IP address.

A defanged IP address replaces every period "." with "[.]".

**First Solution:**
```python
class Solution(object):
    def defangIPaddr(self, address):
        result = ""
        for ch in address:
            if ch == ".":
                result += "[.]";
            else:
                result += ch;
        return result;
```