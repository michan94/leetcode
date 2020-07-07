## Problem

Given an arbitrary ransom note string and another string containing letters from all the magazines, write a function that will return true if the ransom note can be constructed from the magazines ; otherwise, it will return false.

Each letter in the magazine string can only be used once in your ransom note.

## Examples

### Example 1:

Input: ransomNote = "a", magazine = "b"

Output: false

### Example 2:

Input: ransomNote = "aa", magazine = "ab"

Output: false

### Example 3:

Input: ransomNote = "aa", magazine = "aab"

Output: true

**First Solution:**
```python
class Solution(object):
    def canConstruct(self, ransomNote, magazine):
        """
        :type ransomNote: str
        :type magazine: str
        :rtype: bool
        """
        mag = {}
        for letter in magazine:
            if letter in mag:
                mag[letter] += 1
            else:
                mag[letter] = 1
        for letter in ransomNote:
            if letter in mag:
                mag[letter] -= 1
                if mag[letter] < 0:
                    return False
            else:
                return False
        return True
```