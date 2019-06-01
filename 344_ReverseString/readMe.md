## Problem Statement
Write a function that reverses a string. The input string is given as an array of characters ```char[]```.

__Do not allocate extra space for another array__, you must do this by __modifying the input array__ in-place with O(1) extra memory.

You may assume all the characters consist of printable ascii characters.

 

Example 1:
```
Input: ["h","e","l","l","o"]
Output: ["o","l","l","e","h"]
```

Example 2:
```
Input: ["H","a","n","n","a","h"]
Output: ["h","a","n","n","a","H"]
```
## Result
In addition to my usual approach, LeetCode's Recursion I class also require you to approach this problem using Recursion so I uploaded two solutions.

#### Normal Approach
My normal approach beats:
* 100.00% of all Java submissions running-time wise.
* 63.90% of all Java submissions memory-usage wise.
* O(n)

#### Recursive Approach
My recursive approach beats:
* 44.68% of all Java submissions running-time wise.
* 5.80% of all Java submissions memory-usage wise.
* O(n)
* __Note:__ Technically you don't really need recursion for this question. I just did it because of the extra requirement from the class.
