## Problem Statement

Given a string **s** and a string **t**, check if s is **subsequence** of t.

You may assume that:
* there is only lower case English letters in both s and t. 
* t is potentially a very long (length ~= 500,000) string, and s is a short string (<=100).

A subsequence of a string is a new string which is formed from the original string by deleting some (can be none) of the characters without disturbing the relative positions of the remaining characters. 
(ie, ```"ace"``` is a subsequence of ```"abcde"``` while ```"aec"``` is not).

__Example 1:__
```
s = "abc", t = "ahbgdc"

Return true.
```
__Example 2:__
```
s = "axc", t = "ahbgdc"

Return false.
```
__Follow up:___
If there are lots of incoming S, say S<sub>1</sub>, S<sub>2</sub>, ... , S<sub>k</sub> where k >= 1 Billion, and you want to check one by one to see if T has its subsequence. 

In this scenario, how would you change your code?

## Result:
I came up with two solutions for this question: one brute-force and one much more elegant.

### Brute-force
* My brute-force solution uses a for-loop that iterate over each character of s.
* For every character in s, I use a while loop to traverse t finding the first instance of that character in s. 
* The index of the found character if kept track by variable indexT.
* The search for the next character in s would start at the last indexT + 1, instead of from the beginning. This is to make sure the matching character would be in order according to s.
* If the character is not found, indexT > length of T. If the current character we are searching for is not even the last character of s, we know s is not a subsequence of t.
* Thus, if the original for-loop manages to exit, it means s is a subsequence of t.

My brute-force solution beats:
* 26.25% all Java submissions running-time wise.
* 99.70% all Java submissions memory-usage wise.
* __O(n + m)__ where n = length of s and m = length of t

 ### Elegant-solution
* My elegant solution uses String method indexOf(String substring, int fromIndex) to search for the character in c.
* When the character is found in t, I update the pointer currentIndexT to hold the current index of that matched character.
* I repeat the search for the next character in s using indexOf() method but this time from the last IndextT + 1


My elegant solution beats:
* 100.00 % all Java submissions running-time wise.
* 99.87% all Java submissions memory-usage wise.
* __O(n + m)__ where n = length of s and m = length of t


