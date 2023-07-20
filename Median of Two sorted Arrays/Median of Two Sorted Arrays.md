# Median of Two Sorted Arrays
This is a **Hard Level** Leetcode problem.
## Problem Description
Given two sorted arrays nums1 and nums2 of sizes m and n respectively, you need to find the median of the two sorted arrays.

## Python Solution
```py
class Solution(object):
    def findMedianSortedArrays(self, nums1, nums2):
        """
        :type nums1: List[int]
        :type nums2: List[int]
        :rtype: float
        """
        import math
        array = nums1 + nums2
        size = len(array)
        array.sort()

        if size % 2 == 0:
            return (array[size // 2 - 1] + array[size // 2]) / 2.0
        else:
            return array[size // 2]
```
The given Python solution provides a class Solution with a method findMedianSortedArrays that takes in two sorted arrays nums1 and nums2 of sizes m and n respectively. The method finds the median of the combined sorted array.
### Working
- The given code in could be executed on any standardized python environment or IDE e.g. *VScode, Jupyter Notebook, Leetcode IDE etc*, by typing the following command in the terminal:
```py
python streamlit.py
```
- The method first concatenates the two arrays nums1 and nums2 into a new array array.
- The size of the combined array array is determined using len(array).
- The array is then sorted in ascending order using array.sort().
- The median of the combined array is calculated based on whether the total size is even or odd.
- If the size is even, the median is the average of the two middle elements.
- If the size is odd, the median is the middle element.
- The method returns the calculated median as a floating-point number.
## Results
This solution efficiently finds the median of the two sorted arrays by merging them into a single sorted array and calculating the median based on the size of the array.This code's memory usage gives a **97.32%** of the Beat score among other solutions and beats **77.80%** of the runtime.