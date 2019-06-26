## Problem Statement
Given an array of integers nums **sorted in ascending order**, find the starting and ending position of a given target value.

Your algorithm's runtime complexity must be in the order of **O(log n)**.

If the target is not found in the array, return [-1, -1].


**Example 1:**
```
Input: nums = [5,7,7,8,8,10], target = 8
Output: [3,4]
```
**Example 2:**
```
Input: nums = [5,7,7,8,8,10], target = 6
Output: [-1,-1]
```

## Result
**Brute-Force**
My brute-force solution scan the array from the beginning first to find the first instance of the number, it then scans the array from the back to find the last instance of the target number.
If none is found, it returns [-1,-1].

This solution beats:
* 25.11% of all Java submissions running-time wise
* 100.00% of all Java submissions memory-wise
* __O(n)__

**Elegant Binary Search Solution**
My elegant solution uses binary search to look for the target number in the array. 
Once of the number is found, it scans backward to see if any same target number exists to find the very first instance.
Then, from the position of the orginal target found, it scans forward to find the last instance of the number in the array.

This solution beats:
* 100.00% of all Java submissions running-time wise.
* 100.00% of all Java submissions memory-wise.
* __O(log<sub>2</sub>n)__
