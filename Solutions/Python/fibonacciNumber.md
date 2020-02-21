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
        if N in cache:
            return cache[N];
        if N < 2:
            return N;
        else:
            result = self.fib(N-1) + self.fib(N-2);
        cache[N] = result;
        return result;
```