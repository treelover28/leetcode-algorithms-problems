## Problem Statement

Given a binary tree and a sum, determine if the tree has a __root-to-leaf path__ such that adding up all the values along the path equals the given sum.

Note: A leaf is a node with no children.

__Example:__
<pre>
Given the below binary tree and sum = 22,

      <b>5</b>
     / \
    <b>4</b>   8
   /   / \
  <b>11</b>  13  4
 /  \      \
7    <b>2</b>      1

return true, as there exist a root-to-leaf path 5->4->11->2 which sum is 22.
</pre>

## Result
My solution beats:
* 100.00% all Java submissions running-time wise.
* 93.80% all Java submissions memory-usage wise.
* __O(n)__
