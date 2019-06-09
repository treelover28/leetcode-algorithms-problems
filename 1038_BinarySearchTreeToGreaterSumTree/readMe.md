## Problem Statement
Given the root of a **binary search tree** with distinct values, modify it so that every node has a new value equal to the sum of the values of the original tree that are **greater than or equal to node.val.**

As a reminder, a binary search tree is a tree that satisfies these constraints:

* The left subtree of a node contains only nodes with keys less than the node's key.
* The right subtree of a node contains only nodes with keys greater than the node's key.
* Both the left and right subtrees must also be binary search trees.
 

**Example 1:**
![gst](https://user-images.githubusercontent.com/50902696/59156514-f9d94900-8a59-11e9-9161-b7952f847595.png)
```
Input: [4,1,6,0,2,5,7,null,null,null,3,null,null,null,8]
Output: [30,36,21,36,35,26,15,null,null,null,33,null,null,null,8]
```
**Note:**
* The number of nodes in the tree is between 1 and 100.
* Each node will have value between 0 and 100.
* The given tree is a binary search tree.

## Result
I came up with 3 different solutions: 2 brute-forces and 1 elegant.

**Brute-force 1**:
* My first brute-force solution traverse the tree inorderly and add all values into an Array.
* It then traverse the tree inorderly again, but this at each node, it would compare node.val to all values stored in the array.
* sum += all values in array that >= node.val
* set node.val = sum;
* Keep doing so until it has finished traversing the whole tree.

This algorithm beats:
* 10.25% all Java submissions running-time wise.
* 99.50% all Java submissions memory-usage wise.
* __O(n<sup>2</sup>)__

**Brute-force 2**
* It also traverse the tree inorderly and add all values into an Array.
* It then sort the array using Collections.sort(Array)
* It then traverse the tree inorderly again, but for each node, it would search for the node's position in that array and place into index pos.
* since the array is sorted, sum+= vals[i] where i starts at pos and ends in vals.length would give the sum of all values bigger than current node.val.
* Keep doing so until it has finished traversing the whole tree.
* Equally as inefficient.

This algorithm beats:
* 11.46% all Java submissions running-time wise.
* 97.30% all Java submissions memory-usage wise.
* __O(n<sup>2</sup>)__

**Elegant solution**
* Use recursion to traverse the tree until you reach the right most node (containing the largest value)
* As recursion unwinds upward to smaller nodes, set ```currentSum += node.val``` and set ```node.val = currentSum```
* Thus, when recursion reach the node above, currentSum would always contain the sum of all nodes larger than current node.
* Check if currentNode has left child, make recursive call to the method using left child and repeat upper steps. 
* Since all nodes in left child would be smaller than currentNode, the same logic for currentSum applies

This algorithm beats:
* 100.00% all Java submissions running-time wise.
* 100.00% all Java submissions memory-usage wise.
* __O(n)__


