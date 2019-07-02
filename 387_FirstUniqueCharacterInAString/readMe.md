## Problem Statement

Given a string, find the first non-repeating character in it and return it's index. If it doesn't exist, return -1.

__Examples:__
```
s = "leetcode"
return 0.
```
```
s = "loveleetcode",
return 2.
```
__Note:__ You may assume the string contain only lowercase letters.

## Result
I came up with 2 different approaches to this problem

### HashMap to count word frequency
This approach uses a hashMap to store the characters and their frequency. I then use another loop that scan the string, and return the index of the first 
character whose frequency in the hashMap == 1.

This solution beats:
* 40.38% all Java submissions running-time wise.
* 99.58% all Java submissions memory-wise.
* __O(n)__ - requires 2 passes with optimized solution and 3 with the my first brute force attempt.

### Use character's ASCII values as index of array where each index store the frequency of the character
This approach uses to the character's ASCII values to hash it into an array of 256 slots. 
The first pass initialize the array with the character count at the respective index using ASCII subtraction.
The second pass rescan the string and return the index of the character whose frequency == 1

This solution beats:
* 80.77% all Java submissions running-time wise.
* 99.27% all Java submissions memory-usage wise.
* __O(n)__ - much faster than hashMap approach.
