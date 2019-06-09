## Problem Statment

Write a function to delete a node (except the tail) in a singly linked list, given only access to that node.

Given linked list -- head = [4,5,1,9], which looks like following:

![237_example](https://user-images.githubusercontent.com/50902696/59157362-b3d6b200-8a66-11e9-8a1e-74e695cdb9a2.png)

__Example 1:__
```
Input: head = [4,5,1,9], node = 5
Output: [4,1,9]
Explanation: You are given the second node with value 5, the linked list should become 4 -> 1 -> 9 after calling your function.
```

__Example 2:__
```
Input: head = [4,5,1,9], node = 1
Output: [4,5,9]
Explanation: You are given the third node with value 1, the linked list should become 4 -> 5 -> 9 after calling your function.
 ```

__Note:__
* The linked list will have at least two elements.
* All of the nodes' values will be unique.
* The given node will not be the tail and it will always be a valid node of the linked list.
* Do not return anything from your function.

## Result
I came up with two solutions:

### Brute Force
* Starting from node until the second last node in the list, keep making node.val = node.next.val
* When you reach the second last node in the list, also make it node.val = node.next.val
* Then set the temp.next = null, effectively delete the last node

This solution beats:
* 100.00% all Java submissions running-time wise.
* 98.77% all Java submissions memory-usage wise.
* __O(n)__ where n is the number of nodes left after currentNode in the list that we have to traverse

### Elegant solution
* Set the currentNode.val = nextNode.val so current node's value gets replaced with next one's. 
* Set currentNode's next link to the second node after, effectively deleting the next node with duplicate value. 

This solution beats:
* 100.00% all Java submissions running-time wise.
* 100.00% all Java submissions memory-usage wise.
* __O(1)__ constant!
