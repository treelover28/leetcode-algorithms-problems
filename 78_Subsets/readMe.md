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
### Add new number to all previous subsets
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
* __O(n2<sup>n</sup>)__ (this is the best running-time for this solution)

### Backtracking
I have an index called __start__ that keeps track of where the current nums[i] is. I use a for-loop that traverse that list from the index __start__ to the end of the array, with each new nums[i], we add to a temporary subset, which is then added to the result Powerset. I then make the function call itself recursively, but this time with the index __start__ incremented. The next recursive call, in turn, will add the next nums[i] to our temp subset, and this new subset is added to the powerset again, and the recursive call happens once again with the index __start__ once again incremented. 

Once index __start__ >= nums.length, the for-loop doesn't get initiated, and recursion starts to unwind back to the previous stack where it left off (backtrack). At this point, the loop will add the next nums[i] according to whatever index __start__ was at the recursive frame. 

The process keeps repeating until we have found all possible combinations.

This backtracking solution beats:
* 99.90% all Java submissions running-time wise.
* 100.00% all Java submissions memory-usage wise.
* __O(n2<sup>n</sup>)__
