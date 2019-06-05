## Problem Statement

An array is monotonic if it is either __monotone increasing__ or __monotone decreasing__.

An array A is monotone increasing if for all ```i <= j, A[i] <= A[j].```
An array A is monotone decreasing if for all ```i <= j, A[i] >= A[j].```

Return true __if and only if__ the given array A is monotonic.

 

__Example 1:__
```
Input: [1,2,2,3]
Output: true
```
__Example 2:__
```
Input: [6,5,4,4]
Output: true
```
__Example 3:__
```
Input: [1,3,2]
Output: false
```
__Example 4:__
```
Input: [1,2,4,5]
Output: true
```
__Example 5:__
```
Input: [1,1,1]
Output: true
```
## Result
This solution beats:
* 100.00% all Java submissions running-time wise.
* 97.31% all Java submissions memory-usage wise.
* __O(n)__
