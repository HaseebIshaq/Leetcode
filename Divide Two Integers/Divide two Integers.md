# Integer Division without Using Multiplication, Division, and Mod Operator

## Problem Description

Given two integers `dividend` and `divisor`, divide the two integers without using multiplication, division, and mod operator.

The integer division should truncate toward zero, which means losing its fractional part. For example, 8.345 would be truncated to 8, and -2.7335 would be truncated to -2.

Return the quotient after dividing `dividend` by `divisor`.

### Example:

Input:
```
dividend = 10, divisor = 3
```

Output:
```
3
```

## Python Solution

```python
class Solution:
    def divide(self, dividend, divisor):
        n = 0
        sign = 1
        if dividend < 0:
            sign = -sign
            dividend = abs(dividend)
        if divisor < 0:
            sign = -sign
            divisor = abs(divisor)
        nn = 1
        dvd = dividend
        dvr = divisor
        i = 0
        while dvd >= dvr:
            nn = 1
            dd = dvr
            while dvd >= dd:
                i += nn
                dvd -= dd
                dd += dd
                nn += nn

        ans = i

        if sign < 0:
            ans = -ans
        if ans > 2 ** 31 - 1:
            ans = 2 ** 31 - 1
        if ans < -2 ** 31:
            ans = -2 ** 31
        return ans
```

The given Python solution provides a class `Solution` with a method `divide` that takes two integers `dividend` and `divisor` as input. The method divides the two integers without using multiplication, division, and mod operator and returns the quotient.

### Working
- The given code in could be executed on any standardized python environment or IDE e.g. *VScode, Jupyter Notebook, Leetcode IDE etc*.
- The method first initializes some variables: `n`, `sign`, `nn`, `dvd`, `dvr`, and `i`.
- It handles the signs of both `dividend` and `divisor` separately and keeps track of the final sign of the quotient in the `sign` variable.
- It then iterates through a nested loop to perform the division without using multiplication or division.
- The outer loop runs while `dvd` (current dividend) is greater than or equal to `dvr` (divisor).
- The inner loop doubles the `dvr` (divisor) and the `nn` (multiplier) until `dvd` becomes smaller than `dvr`.
- For each iteration of the inner loop, the quotient is updated in the variable `i`.
- The final result is stored in the `ans` variable, taking the sign into account and ensuring it stays within the 32-bit signed integer range.
- Finally, the method returns the computed quotient `ans`.

## Results
This solution efficiently calculates the quotient of the two integers without using multiplication, division, or mod operator, and it takes care of overflow/underflow issues as well. This code's memory usage gives a **74.86%** of the Beat score among other solutions.