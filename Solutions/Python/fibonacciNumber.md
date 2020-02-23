## Problem

The Fibonacci numbers, commonly denoted F(n) form a sequence, called the Fibonacci sequence, such that each number is the sum of the two preceding ones, starting from 0 and 1. That is,

F(0) = 0,   F(1) = 1


F(N) = F(N - 1) + F(N - 2), for N > 1.

Given N, calculate F(N).

**First Solution:**
```python
class Solution(object):
    def fib(self, N):
        """
        :type N: int
        :rtype: int
        """
        cache = {};
        # Check to see if value already stored
        if N in cache:
            return cache[N];
        # Base case
        if N < 2:
            return N;
        # Recursive calls to solve input if not in dict
        else:
            result = self.fib(N-1) + self.fib(N-2);
        # Store new result;
        cache[N] = result;
        return result;
```
<<<<<<< HEAD

**Second Solution**
```python
class Solution(object):
    def fib(self, N):
        """
        :type N: int
        :rtype: int
        """
        cache = {0 : 0, 1 : 1}
        if N in cache:
            return cache[N];
        else:
            for i in range(2, N + 1):
                cache[i] = self.fib(N-1) + self.fib(N-2);
        return cache[N];
```
=======
>>>>>>> 55bc1c59d2ff2d1632f96fd867bd694756be6e43
