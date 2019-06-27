## Problem Statement
Given a set of **distinct** integers, nums, return all possible subsets (the power set).

__Note:__ The solution set must not contain duplicate subsets.

**Example:**
```
Input: nums = [1,2,3]
Output:
[
  [1],
  [2],
  [3],
  [1,2,3],
  [1,3],
  [2,3],
  [1,2],
  []
]
```

## Result
My algorithm adds a null set to the PowerSet first. 
Afterward, it iterates through nums, add num to deep copies of all previous subsets in PowerSet
Add all the updated subsets back into PowerSet

__For example,__

For 1, PowerSet contains ```[[]]```.
* Add 1 to all subsets in PowerSet, we form ```[1]```
* Add new set to powerSet. 
* powerSet now contains ```[[],[1]]```.

For 2, PowerSet contains ```[[],[1]]```.
* Add 2 to all subsets in PowerSet, we form ```[2], [1,2]```
* Add new sets to powerSet. 
* powerSet now contains ```[[],[1],[2],[1,2]]```.

For 3, PowerSet contains ```[[],[1],[2],[1,2]]```.
* Add 3 to all subsets in PowerSet, we form ```[3], [1,3], [2,3],[1,2,3]```
* Add new sets to powerSet. 
* powerSet now contains ```[[],[1],[2],[1,2],[3],[1,3],[2,3],[1,2,3]]```.

My solution beats:
* 100.00% all Java submissions running-time wise
* 98.92% all Java submissions memory-wise
* __O(2<sup>n</sup>)__ uhhhh O.o


