## Problem Statement
Given two binary trees and imagine that when you put one of them to cover the other, some nodes of the two trees are overlapped while the others are not.

You need to merge them into a new binary tree. The merge rule is that :
* If two nodes **overlap**, then **sum** node values up as the new value of the merged node. 
* Otherwise, the **NOT null** node will be used as the node of new tree.

**Example 1:**
```
Input: 
	Tree 1                     Tree 2                  
          1                         2                             
         / \                       / \                            
        3   2                     1   3                        
       /                           \   \                      
      5                             4   7                  
Output: 
Merged tree:
	     3
	    / \
	   4   5
	  / \   \ 
	 5   4   7
```

## Result
My algorith uses recursion to change Tree1 according to Tree2:
* If a node on Tree1 exist, but a corresponding node on Tree 2 doesn't, we leave the node in Tree1 be.
* If a node on Tree1 doesn't exist, but a corresponding node on Tree2 does, let the existing node replace the null node on Tree1.
* If both nodes exist,just sum up their values.
* Recursively call function on t1.right and t1.left.
* Return fully merged t1 afterward.

My solution beats:
* 99.98% all Java submissions running speed-wise.
* 100.00% all Java submissions memory-usage wise.
* __O(n)__
