## Problem Statement

You are given a binary tree in which each node contains an integer value.

Find the number of paths that sum to a given value.

The path __does not need to start or end at the root or a leaf__,but it must go __downwards__ (traveling only from parent nodes to child nodes).

The tree has no more than 1,000 nodes and the values are in the range -1,000,000 to 1,000,000.

__Example:__
<pre>
root = [10,5,-3,3,2,null,11,3,-2,null,1], sum = 8

      10
     /  \
    <b>5</b>   <b>-3</b>
   / \    \
  <b>3</b>   <b>2</b>   <b>11</b>
 / \   \
3  -2   <b>1</b>

Return 3. The paths that sum to 8 are:

1.  5 -> 3
2.  5 -> 2 -> 1
3. -3 -> 11
</pre>

## Result
My solution beats:
* 100.00% all Java submissions running-time wise.
* 99.26% all Java submissions memory-usage wise.
* __O(n)__

## Additional Reflection: 
This question, in my opinion, is much harder than its predecessor Path Sum I and Path Sum II which were both **Medium** level questions.
There is no way this question is an **Easy**. Should at least be a **Medium** in my opinion.
