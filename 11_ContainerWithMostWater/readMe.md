## Problem Statement

Given n __non-negative integers__ a<sub>1</sub>, a<sub>2</sub>, ..., a<sub>n</sub> , where each represents a point at coordinate (i, a<sub>i</sub>), __n__ vertical lines are drawn such that the two endpoints of line i is at (i, a<sub>i</sub>) and (i, 0).

Find two lines, which together with x-axis forms a container, such that the container contains the most water.

Note: You may not slant the container and __n is at least 2__.
![question_11](https://user-images.githubusercontent.com/50902696/59000222-c0d57600-87c6-11e9-92a0-00a0bfa1b95b.jpg)
 
The above vertical lines are represented by array ```[1,8,6,2,5,4,8,3,7]```. 
In this case, the max area of water (blue section) the container can contain is 49.

__Example:__
```
Input: [1,8,6,2,5,4,8,3,7]
Output: 49
```
## My Result
My brute-force solution beats:
* 25.0% all Java submissions running-time wise.
* 99.93% all Java submissions memory-usage wise.
* __O(n<sup>2</sup>)__
