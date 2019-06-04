## Problem Statement
Find the __kth largest element__ in an unsorted array. 
Note that it is the kth largest element in the sorted order, not the kth distinct element.

__Example 1:__
```
Input: [3,2,1,5,6,4] and k = 2
Output: 5
```

__Example 2:__
```
Input: [3,2,3,1,2,4,5,5,6] and k = 4
Output: 4
```

Note: 
You may assume k is always valid, __1 ≤ k ≤ array's length__.

## Result
My algorithm beats:
* 92.70% of all Java submissions running-time wise
* 96.31% of all Java submissions memory-usage wise
* __O(nlog(n))__ // depends mostly on the sorting algorithm Arrays.sort()
